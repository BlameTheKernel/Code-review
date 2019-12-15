# Code review
Places to look for vulnerabilities

One of the main disadvantages of the C language and its derivates is the lack of a built-in functionality to check that data being copied into a buffer will not be larger than the buffer can hold.

After each malloc() check if the allocation failed and the pointer is not NULL.

Look for random functions. (not enough randomness?)

Look for strcpy, sprintf, strcat, gets and other similar function that doesn¡t check the size of their destination buffers. Check if the destination buffers are properly allocated or has verification of the input size before copying.

Check printf, syslog and others similar for format strings vulnerabilities.

Check and recheck bounds-checks, this mean even if a bound-check exists analyze it because sometimes is not good enough.

Search for loops and loops within loops that process user-defined inputs.

strncat function and others that null-terminates its output can lead to off-by-one vulnerability.

