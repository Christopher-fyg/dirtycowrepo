List of PoCs available
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
  * Usage: `dirtycow file content`
  * Description: Allows user to write on files meant to be read only (android).