# fish-assoc

Associative arrays for fish

This is a (hopefully) fast implementation of associative arrays for fish
relying only on fish shell builtins -- `string` is pretty usefull here...

This enables the broad majority of associative arrays by means of storing
a key-value tuple as a single element in a fish array. Elements in the
tuple are delimited using the ASCII unit separator (codepoint 31).

Some shell metaprogramming trickery is also used here, namely some (ab)use
of `eval` (to avoid unneeded conversion to and from a "true" list), in
addition to the fact that scope shadowing is enabled for all functions in
the library.

Usage is pretty simple, and supports a syntax similar to `set`:

```fish

assoc.set name[key] value
assoc.get name[key]
assoc.rm  name[key]

assoc.has_key name[key]

```
