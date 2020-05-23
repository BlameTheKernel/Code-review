# Code review
## Places to look for vulnerabilities

One of the main disadvantages of the C language and its derivates is the lack of a built-in functionality to check that data being copied into a buffer will not be larger than the buffer can hold.

- After each malloc() check if the allocation failed and the pointer is not NULL.
- Look for random functions. (not enough randomness?)
- Look for strcpy, sprintf, strcat, gets and other similar function that doesn¡t check the size of their destination buffers. Check if the destination buffers are properly allocated or has verification of the input size before copying.
- Check printf, syslog and others similar for format strings vulnerabilities.
- You can find a possibly format string vulnerability but it's needed to trace back the flow of data to see if the attacker has control over the input.
- Check and recheck bounds-checks, this mean even if a bound-check exists analyze it because sometimes is not good enough.
- Check the size of the input string.
- Search for loops, parsing loops and loops-within-loops, that process user-defined inputs.
- strncat function and others that null-terminates its output can lead to off-by-one vulnerability.
- Strings must finish with a null byte, check it.
- Look for global pointers. Doble free vulnerabilities are found most commonly when heap buffers are stored in global pointers.
- Check Integer type ranges are properly checked.
- Check input values are restricted to a valid range based on their intended use.

Integers that do not require negative values are declared as unsigned and properly range-checked for upper and lower bounds.
Operations on integers originating from untrusted sources are performed using a safe integer library.
