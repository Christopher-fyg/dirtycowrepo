## Table of PoCs
| Link | Usage | Description | Family |
|---|---|---|---|---|---|---|
| [dirtyc0w.c](https://github.com/dirtycow/dirtycow.github.io/blob/master/dirtyc0w.c) | `./dirtyc0w file content` | Read-only write | /proc/self/mem |
| [cowroot.c](https://gist.github.com/rverton/e9d4ff65d703a9084e85fa9df083c679) | `./cowroot` | SUID-based root | /proc/self/mem |
| [dirtycow-mem.c](https://gist.github.com/scumjr/17d91f20f73157c722ba2aea702985d2) | `./dirtycow-mem` | libc-based root | /proc/self/mem |
| [pokemon.c](https://github.com/dirtycow/dirtycow.github.io/blob/master/pokemon.c) | `./d file content` | Read-only write | PTRACE_POKEDATA |
| [dirtycow.cr](https://github.com/xlucas/dirtycow.cr) | `dirtycow --target --string --offset` | Read-only write | /proc/self/mem |
| [dirtyc0w.c](https://github.com/timwr/CVE-2016-5195) | `./dirtycow file content` | Read-only write | /proc/self/mem |
| [dirtycow.rb](https://github.com/rapid7/metasploit-framework/pull/7476) | `use exploit/linux/local/dirtycow` and `run` | SUID-based root | /proc/self/mem |
| [0xdeadbeef.c](https://github.com/scumjr/dirtycow-vdso) | `./0xdeadbeef` | vDSO-based root | PTRACE_POKEDATA |
| [naughtyc0w.c](https://gist.github.com/mak/c36136ccdbebf5ecfefd80c0f2ed6747) | `./c0w suid` | SUID-based root | /proc/self/mem |
| [c0w.c](https://gist.github.com/KrE80r/42f8629577db95782d5e4f609f437a54) | `./c0w` | SUID-based root | PTRACE_POKEDATA|
| [dirty_passwd_adjust_cow.c](https://gist.github.com/ngaro/05e084ca638340723b309cd304be77b2) | `./dirty_passwd_adjust_cow` | current user becomes UID 0 | /proc/self/mem |

## List of PoCs
* https://github.com/dirtycow/dirtycow.github.io/blob/master/dirtyc0w.c
  * Allows user to write on files meant to be read only.
* https://gist.github.com/rverton/e9d4ff65d703a9084e85fa9df083c679
  * Gives the user root by overwriting `/usr/bin/passwd` or a suid binary.
* https://gist.github.com/scumjr/17d91f20f73157c722ba2aea702985d2
  * Gives the user root by patching libc's getuid call and invoking `su`.
* https://github.com/dirtycow/dirtycow.github.io/blob/master/pokemon.c
  * Allows user to write on files meant to be read only.
* https://github.com/xlucas/dirtycow.cr
  * Allows a user to write on files meant to be read only.
* https://github.com/timwr/CVE-2016-5195
  * Allows user to write on files meant to be read only (android).
* https://github.com/rapid7/metasploit-framework/pull/7476
  * Metasploit module based on the `cowroot` PoC.
* https://github.com/scumjr/dirtycow-vdso
  * Gives the user root by patching the vDSO escapes containers/SELinux doesn't need suid.
* https://gist.github.com/mak/c36136ccdbebf5ecfefd80c0f2ed6747
  * Gives the user root by injecting shellcode into a SUID file.
* https://gist.github.com/KrE80r/42f8629577db95782d5e4f609f437a54
  * Gives the user root by injecting shellcode into a SUID file using PTRACE_POKEDATA .

