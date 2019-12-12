# Code-review
Places to look for vulnerabilities

One of the main disadvantages of the C language and its derivates is the lack of a built-in functionality to check that data being copied into a buffer will not be larger than the buffer can hold.

After each malloc() check if the allocation failed and the pointer is not NULL.
Look for random functions. (not enough randomness?)

