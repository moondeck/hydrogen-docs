#System call interface

This document describes the Hydrogen system call interface. As this is only a design document now, it might change in the future, and API stability is not guranteed. Hydrogen is not a *nix, so system calls are not standard, however most of them should be compatible.

#Program operation

##exec(file)

Executes a file from disk, closing the parent process. Usage:

    exec(/bin/sh)

Returns -1 on failure, otherwise returns 0

##fork()

Forks the current process and creates a child process.

Returns child's PID on success, -1 on failure

#File operations

##load(file, address)

Loads a file into memory at an address. Usage:

    load(/bin/sh)

Returns address to the file in memory on success, -1 on failure

##open(file)

Opens a file. Usage:

    open(/cfg/boot.cfg)

Returns a file descriptor on success, -1 on failure

##close(fd)

Closes a file descriptor. After that, the file descriptor variable is set to 0

##write(fd, *data, length)

Writes length bytes from *data pointer to the file descriptor fd. Usage:

    write(filedesc, &somestuff, strlen(somestuff));

Returns bytes written on success, -1 if no writing happened.
