# boltDB

An sqlite clone

Learning from:
- https://cstack.github.io/db_tutorial/
- https://en.wikipedia.org
- https://stackoverflow.com
- https://www.youtube.com/@BroCodez

## Things I Learned

### read-eval-print Loop (REPL)

A read–eval–print loop (REPL), also termed an interactive toplevel or language shell, is a simple interactive computer programming environment that takes single user inputs, executes them, and returns the result to the user; a program written in a REPL environment is executed piecewise.  
The term usually refers to programming interfaces similar to the classic Lisp machine interactive environment. Common examples include command-line shells and similar environments for programming languages, and the technique is very characteristic of scripting languages.  

In a REPL, the user enters one or more expressions (rather than an entire compilation unit) and the REPL evaluates them and displays the results.  
- The read function accepts an expression from the user, and parses it into a data structure in memory. 
- The eval function takes this internal data structure and evaluates it. 
- The print function takes the result yielded by eval, and prints it out to the user. If it is a complex expression, it may be pretty-printed to make it easier to understand.  
The development environment then returns to the read state, creating a loop, which terminates when the program is closed.

### Data Buffer

In computer science, a data buffer (or jsut buffer) is a region of a memory used to store data temporarily while it is being moved from one place to another.  
Buffers can be implemented in a fixed memory location in hardware or by using a virtual data buffer in software that points at a location in the physical memory.  
Buffers can increase application performance by allowing synchronous operations such as file reads or writes to complete quickly instead of blocking while waiting for hardware interrupts to access a physical disk subsystem; instead, an operating system can immediately return a successful result from an API call, allowing an application to continue processing while the kernel completes the disk operation in the background.  
Further benefits can be achieved if the application is reading or writing small blocks of data that do not correspond to the block size of the disk subsystem, which allows a buffer to be used to aggregate many smaller read or write operations into block sizes that are more efficient for the disk subsystem, or in the case of a read, sometimes to completely avoid having to physically access a disk.

### `getline()`

To read a line of input, use `getline()`.

```c
ssize_t getline(char **lineptr, size_t *n, FILE *stream)
```

- `lineptr`: a pointer to the variable we use to point to the buffer containing the read line.  
- If it set to `NULL`, it is mallocatted by `getline` and should thus be freed by the user, even if the command fails.
- `n`: a pointer to the variable we use to save the size of allocated buffer.
- `stream`: the input stream to read from.
- `return value`: the number of bytes read, which may be less than the size of the buffer.

### C Infinite Loop

C has no built-in boolean types. So it doesn't know what true is.  
To make an infinite loop:

```c
while(1) {
    ...
}
```

or

```c
for(;;) {
    ...
}
```

### SQLite Architecture

![SQLite Architecture Diagram](/sqlite-archtecture.png)

### Enumerated type

In computer programming, an enumerated type (also called enumeration, enum, or factor in the R programming language, and a categorical variable in statistics) is a data type consisting of a set of named values called elements, members, enumeral, or enumerators of the type.  
The enumerator names are usually identifiers that behave as constants in the language.  
A variable that has been declared as having an enumerated type can be assigned any of the enumerators as a value.  
In other words, an enumerated type has values that are different from each other, and that can be compared and assigned, but are not specified by the programmer as having any particular concrete representation in the computer's memory; compilers and interpreters can represent them arbitrarily.