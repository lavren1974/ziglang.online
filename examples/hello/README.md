# ziglang.online


## Hell02

```zig title "hello.zig"

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