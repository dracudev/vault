The `fcntl.h` and `unistd.h` libraries in C provides advanced file control operations. Below are key functions and their usage.
### open()

- **Description**: Open a file.
- **Prototype**: `int open(const char *pathname, int flags, mode_t mode);`
    - **Parameters**:
        - **pathname**: Path to the file.
        - **flags**: Mode in which to open the file.
            - `O_RDONLY`: Open for reading only.
            - `O_WRONLY`: Open for writing only.
            - `O_RDWR`: Open for reading and writing.
            - `O_CREAT`: Create the file if it does not exist.
            - `O_TRUNC`: Truncate the file to length 0 if it exists.
            - `O_APPEND`: Write at the end of the file.
        - **mode**: File permissions if creating a new file (e.g., `S_IRUSR | S_IWUSR` for read and write permissions for the owner).
    - **Returns**: File descriptor on success, `-1` on error.
```c
#include <fcntl.h>
#include <unistd.h>
#include <stdio.h>

int main() {
    int fd = open("file.txt", O_WRONLY | O_CREAT | O_TRUNC, S_IRUSR | S_IWUSR);
    if (fd == -1) {
        perror("Error opening file");
        return -1;
    }

    const char *text = "Hello, world!";
    if (write(fd, text, strlen(text)) == -1) {
        perror("Error writing to file");
        close(fd);
        return -1;
    }

    close(fd);
    return 0;
}
```
### read()

- **Description**: Read from a file.
- **Prototype**: `ssize_t read(int fd, void *buf, size_t count);`
    - **Parameters**:
        - **fd**: File descriptor to read from.
        - **buf**: Buffer to read data into.
        - **count**: Number of bytes to read.
    - **Returns**: Number of bytes read on success, `-1` on error.
```c
#include <fcntl.h>
#include <unistd.h>
#include <stdio.h>

int main() {
    int fd = open("file.txt", O_RDONLY);
    if (fd == -1) {
        perror("Error opening file");
        return -1;
    }

    char buffer[100];
    ssize_t bytesRead = read(fd, buffer, sizeof(buffer) - 1);
    if (bytesRead == -1) {
        perror("Error reading file");
        close(fd);
        return -1;
    }

    buffer[bytesRead] = '\0';
    printf("Read: %s\n", buffer);

    close(fd);
    return 0;
}
```
### write()

- **Description**: Write to a file.
- **Prototype**: `ssize_t write(int fd, const void *buf, size_t count);`
    - **Parameters**:
        - **fd**: File descriptor to write to.
        - **buf**: Buffer containing data to write.
        - **count**: Number of bytes to write.
    - **Returns**: Number of bytes written on success, `-1` on error.
```c
#include <fcntl.h>
#include <unistd.h>
#include <stdio.h>
#include <string.h>

int main() {
    // Open a file for writing, create if it does not exist, truncate if it does
    int fd = open("example.txt", O_WRONLY | O_CREAT | O_TRUNC, S_IRUSR | S_IWUSR);
    if (fd == -1) {
        perror("Error opening file");
        return -1;
    }

    // Data to be written to the file
    const char *text = "Hello, world!\n";

    // Write data to the file
    ssize_t bytesWritten = write(fd, text, strlen(text));
    if (bytesWritten == -1) {
        perror("Error writing to file");
        close(fd);
        return -1;
    }

    // Close the file
    close(fd);

    printf("Successfully written %zd bytes to the file.\n", bytesWritten);
    return 0;
}

```
### close()

- **Description**: Close a file.
- **Prototype**: `int close(int fd);`
    - **Parameters**:
        - **fd**: File descriptor to close.
    - **Returns**: `0` on success, `-1` on error.