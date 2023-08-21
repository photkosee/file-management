# File Management
> Note that the code here is not the complete version of this project. The complete code is maintained on GitLab and could be published after 2025 due to UNSW policy. </br>
Please contact me to review the complete version of the code in person.

Implement `open()`, `read()`, `write()`, `lseek()`, `close()`, and `dup2()` <br/>
Using Per-Process fd table with global open file table<br/>

## Task
Of the full range of system calls that are listed in `kern/include/kern/syscall.h`, **your task is to implement the following file-based system calls**: open, read, write, lseek, close, dup2, and document your design. Note: You will be writing the kernel code that implements part of the system call functionality within the kernel. You are not writing the C stubs that user-level applications call to invoke the system calls. The userland stubs are automatically generated when you build OS/161 in `build/userland/lib/libc/syscalls.S`, which you should not modify.

It's crucial that your syscalls handle all error conditions gracefully (i.e., without crashing OS/161.) no matter what an application requests. Your code should also be memory leak free. You should consult the [OS/161 man pages](https://cgi.cse.unsw.edu.au/~cs3231/18s1/os161/man/) (also included in the distribution) and understand the system calls that you must implement. Your system calls must return the correct value (in case of success) or an appropriate error code (in case of failure) as specified in the man pages. Some of the auto-marking scripts rely on the return of error codes. However, we are lenient about the specific code in the case of potential ambiguity and which error code would be most appropriate. It's also not necessary to generate all error codes listed in the man pages.

The file `userland/include/unistd.h` contains the user-level interface definition of the system calls. This interface is different from that of the kernel functions that you will define to implement these calls. You need to design the kernel side of this interface. The function prototype for your interface can be put in `kern/include/syscall.h`. The integer codes for the calls are defined in `kern/include/kern/syscall.h`. <br>


![FM](https://github.com/PhotKosee/file-management/assets/114990364/59382449-4186-4d82-a616-3fb00e0f2c4f)

## System Call Interface
- `int open(const char *filename, int flags)`
- `int open(const char *filename, int flags, mode_t mode);int close(int fd)`
- `ssize_t read(int fd, void *buf, size_t buflen)`
- `ssize_t write(int fd, const void *buf, size_t nbytes);int dup2(int oldfd, int newfd)`
- `off_t lseek(int fd, off_t pos, int whence)`
