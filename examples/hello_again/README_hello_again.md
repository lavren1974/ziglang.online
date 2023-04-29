

#### hello.zig
```zig

const print = @import("std").debug.print;

pub fn main() void {
    print("Hello, world!\n", .{});
}

```

```
$ zig build-exe hello_again.zig

$ ./hello_again
Hello, world!
```