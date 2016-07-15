
# fromArgs 1.0.0 ![stable](https://img.shields.io/badge/stability-stable-4EBA0F.svg?style=flat)

Create a `Function` that takes an `Arguments` object, and returns a nested value
using an index (defaults to `0`) and a key (dot-notation is allowed).

```coffee
fromArgs = require "fromArgs"

arg1 = { key: 1 }
arg2 = { key: 2 }
arg2.nested = { key: 3 }

# Get the 'key' property from the first argument.
getValue = fromArgs "key"
getValue arg1, arg2 # => 1

# Get the 'key' property from the second argument.
getValue = fromArgs 1, "key"
getValue arg1, arg2 # => 2

# Get the 'nested.key' property from the second argument.
getValue = fromArgs 1, "nested.key"
getValue arg1, arg2 # => 3

# Get the first argument.
getValue = fromArgs 0
getValue arg1, arg2 # => { key: 1 }
```
