This is a list of PoC's for DirtyCow(CVE-2016-5195)

dirtyc0w.c- https://github.com/dirtycow/dirtycow.github.io/blob/master/dirtyc0w.c
Works via /proc/self/maps. With this you can write to read only files.
pokemon.c- https://github.com/dirtycow/dirtycow.github.io/blob/master/pokemon.c

Works via PTRACE_POKEDATA. With this you can write to read only files for systems that /proc/self/mem is not writable to (ie. RHEL 5 RHEL 6). 