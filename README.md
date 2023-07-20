# File Management
> The source code is maintained on GitLab and could be published after 2025 due to UNSW policy. </br>
Please reach out to me to review the code in person.

Implement open(), read(), write(), lseek(), close(), and dup2() <br/>
Using Per-Process fd table with global open file table<br/>


![FM](https://github.com/PhotKosee/file-management/assets/114990364/59382449-4186-4d82-a616-3fb00e0f2c4f)

## System Call Interface
- `int open(const char *filename, int flags)`
- `int open(const char *filename, int flags, mode_t mode);int close(int fd)`
- `ssize_t read(int fd, void *buf, size_t buflen)`
- `ssize_t write(int fd, const void *buf, size_t nbytes);int dup2(int oldfd, int newfd)`
- `off_t lseek(int fd, off_t pos, int whence)`
