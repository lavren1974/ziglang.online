# ziglang.online


#### hello.zig
```zig

const std = @import("std");

pub fn main() !void {
    const stdout = std.io.getStdOut().writer();
    try stdout.print("Hello, {s}!\n", .{"world"});
}
```

```
$ zig build-exe hello.zig

$ ./hello
Hello, world!
```

`const std = @import("std");`

This line imports the standard library and assigns it to the constant identifier `std`. The `@import` keyword is a built-in function in Zig that imports a package. The standard library provides various utility functions, including I/O operations.

`pub fn main() !void {`

This line defines the entry point of the program, the `main` function, which is public (`pub`) and returns an error union type `!void`. In Zig, the ! denotes an error union, which means the function can return either the specified type (`void` in this case) or an error. void is a type with no value, indicating that the main function does not return any value.

`const stdout = std.io.getStdOut().writer();`

This line gets the standard output (stdout) stream and creates a writer for it. `std.io.getStdOut()` returns a reference to the stdout file, and `.writer()` creates a buffered writer for the file. The result is assigned to the constant identifier `stdout`.

`try stdout.print("Hello, {s}!\n", .{"world"});`

This line prints the string "Hello, world!" followed by a newline character to the stdout using the `print` function of the buffered writer. The `try` keyword is used to handle errors; if the `print` function returns an error, the program will return the error and terminate immediately. The format string `"Hello, {s}!\n"` contains a placeholder `{s}` that will be replaced by the corresponding value provided in the arguments. The `.{}` syntax is used to create an anonymous struct, which in this case has one field "s" with the value "world". The `print` function replaces the placeholder `{s}` with the value "world" before writing the output.

`}`

This line simply closes the main function's block of code.

When this program is executed, it will print "Hello, world!" followed by a newline character to the console.