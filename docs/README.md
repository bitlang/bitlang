# Bit Language

## Bit Code
If a Bit file is code, it should start with a shebang line that relates to Bit. For example, the following are all valid:
```
#!/bin/bitsh
#!/usr/bin/bitlang
#! bit
```
Bit Code also functions as a shell, but may not be POSIX compliant (yet).

* Read more about Bit [here][code].

## Bit Data
If a Bit file lacks a code header, it is assumed to be Bit data. Bit data files follow a format where every statement can be assumed to be prefixed with `const`. Because of this, only primitives can be used and directives like `use` are blocked. Bit data files attempt to assume the type, allowing for strings to be expressed without quotation marks, for example. (If you want this behavior in Bit scripts, use the compiler magic comment `#[features string_default_value]` near the top of the file.)

However, Bit data files can include other Bit data and markup files:
```bit
include author.bit

name bitclock
description "A simple app to measure the time"
dependencies
    gh:bitlang/time 1.0.2
```

* Read more about Bit data [here][data].

[code]: code/
[data]: code/var/