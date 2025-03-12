### Thoery
Buffer overflow is a common security vulnerability that occurs when more data is written to a buffer than it can hold. A buffer is a contiguous block of memory that is allocated to store data temporarily, such as a string of text or an array of integers. When a program writes data beyond the bounds of a buffer, it can overwrite adjacent memory locations, leading to unpredictable behavior. This vulnerability is particularly prevalent in languages like C and C++, where memory management is manual, and there are no built-in safeguards to prevent overwriting memory.

##### Key Concepts of Buffer Overflow
<p>
Memory Management: In programming languages like C and C++, memory management is handled manually. This means developers must allocate and deallocate memory as needed. If they allocate a buffer but don't ensure that the data written to it fits within its boundaries, a buffer overflow can occur.
</p>
<p>
Stack: Buffers often reside in the stack, a memory region used for local variables and function call management. Stack-based buffer overflows are the most common because local variables are stored contiguously. When a buffer overflows, it can overwrite adjacent memory in the stack frame, including critical elements like return addresses and function pointers, leading to unpredictable behavior or exploitation.
</p>

##### How Buffer Overflow Happens?
<p>
Lack of Bounds Checking: Many standard C library functions, such as strcpy, gets, and scanf, do not check the size of the destination buffer. For instance, if a program uses strcpy to copy a 20-character string into a 10-character buffer, the extra 10 characters overwrite whatever comes after the buffer in memory.</p>
<p>
User Input: Buffer overflows often occur when a program accepts user input without validating its size. For example, a program might prompt for a username and store it in a fixed-size buffer. If the user enters a string longer than the buffer’s capacity, the excess data overflows into adjacent memory.
</p>