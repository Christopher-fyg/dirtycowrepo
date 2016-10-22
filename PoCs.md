## Table of PoCs
| Link | Usage | Description | Family | Notes |
|---|---|---|---|---|---|---|
| [dirtyc0w.c](https://github.com/dirtycow/dirtycow.github.io/blob/master/dirtyc0w.c) | `./dirtyc0w` file content | Read-only write | /proc/self/mem |  |
| [cowroot.c](https://gist.github.com/rverton/e9d4ff65d703a9084e85fa9df083c679) | `./cowroot` | SUID-based root | /proc/self/mem |  |
| [dirtycow-mem.c](https://gist.github.com/scumjr/17d91f20f73157c722ba2aea702985d2) | `./dirtycow-mem` | libc-based root | /proc/self/mem |  |
| [pokemon.c](https://github.com/dirtycow/dirtycow.github.io/blob/master/pokemon.c) | `./d file content` | Read-only write | PTRACE_POKEDATA | Works in RHEL5 and 6 |
| [dirtycow.cr](https://github.com/xlucas/dirtycow.cr) | `dirtycow --target --string --offset` | Read-only write | /proc/self/mem | Supports offsets |
| [dirtyc0w.c](https://github.com/timwr/CVE-2016-5195) | `./dirtycow file content` | Read-only write | /proc/self/mem | Android root |
| [dirtycow.rb](https://github.com/rapid7/metasploit-framework/pull/7476) | `use exploit/linux/local/dirtycow` and `run` | SUID-based root | /proc/self/mem | metasploit module |
| [0xdeadbeef.c](https://github.com/scumjr/dirtycow-vdso) | `./0xdeadbeef` | vDSO-based root | PTRACE_POKEDATA | Works on SELinux and containers |
| [naughtyc0w.c](https://gist.github.com/mak/c36136ccdbebf5ecfefd80c0f2ed6747) | `./c0w suid` | SUID-based root | /proc/self/mem |  |

## List of PoCs
* https://github.com/dirtycow/dirtycow.github.io/blob/master/dirtyc0w.c
  * Usage: `./dirtyc0w` file content
  * Description: Allows user to write on files meant to be read only (uses `/proc/self/mem`).
* https://gist.github.com/rverton/e9d4ff65d703a9084e85fa9df083c679
  * Usage: `./cowroot`
  * Description: Gives the user root by overwriting `/usr/bin/passwd` or a suid binary.
* https://gist.github.com/scumjr/17d91f20f73157c722ba2aea702985d2
  * Usage: `./dirtycow-mem`
  * Description: Gives the user root by patching libc's getuid call and invoking `su`.
* https://github.com/dirtycow/dirtycow.github.io/blob/master/pokemon.c
  * Usage: `./d file content`
  * Description: Allows user to write on files meant to be read only (**does not use** `/proc/self/mem`).
* https://github.com/xlucas/dirtycow.cr
  * Usage: `dirtycow --target /path/to/root/file --string "string to write" --offset <offset_in_file>`
  * Description: Allows a user to write on files meant to be read only (uses `/proc/self/mem`).
* https://github.com/timwr/CVE-2016-5195
  * Usage: `./dirtycow file content`
  * Description: Allows user to write on files meant to be read only (android).
* https://github.com/rapid7/metasploit-framework/pull/7476
  * Usage: `use exploit/linux/local/dirtycow` and `run`
  * Description: Metasploit module based on the `cowroot` PoC.
* https://github.com/scumjr/dirtycow-vdso
  * Usage: `./0xdeadbeef`
  * Description: Gives the user root by patching the vDSO (**does not use** `/proc/self/mem`) escapes containers/SELinux doesn't need suid.
* https://gist.github.com/mak/c36136ccdbebf5ecfefd80c0f2ed6747
  * Usage: `./c0w suid`
  * Description: Gives the user root by injecting shellcode into a SUID file.
