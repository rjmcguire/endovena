# endovena
[![Dub version](https://img.shields.io/dub/v/endovena.svg)](https://code.dlang.org/packages/endovena)
[![Build Status](https://travis-ci.org/o3o/endovena.svg?branch=master)](https://travis-ci.org/o3o/endovena)
[![Dub download Status](https://img.shields.io/dub/dt/endovena.svg)](https://code.dlang.org/packages/endovena)



Simple dependency injection framework for D.

Based on [Jakub Stasiak](https://github.com/jstasiak/dejector) similar work.

## Example usage
``` d
import std.conv : to;
import std.stdio : writefln;

import endovena;

interface IGreeter {
    string greet();
}

class Greeter: IGreeter {
    string greet() { return "Hello!"; }
}

void main() {
    Container container;
    container.register!(IGreeter, Greeter);
    auto greeter = container.get!IGreeter();
    writefln(greeter.greet)
}
```

Output:
``` d
    Hello!
```
See also directory `tests/` and [wiki](https://github.com/o3o/endovena/wiki).

## Compiling
You can use [dub](https://github.com/rejectedsoftware/dub):
```
$ dub build
```

Or (on linux) makefile:
```
$ make
```

## Running tests
You need to have [dub](https://github.com/rejectedsoftware/dub)  >= 0.9.21 installed and reacheble from your PATH.

```
dub --verbose test
```
or with make:
```
$ make
```

## Related Projects
* [dejector](https://github.com/jstasiak/dejector)
* [deject](https://github.com/bgertzfield/deject)
* [poodinis](https://github.com/mbierlee/poodinis)

## References
* [dryioc](https://bitbucket.org/dadhi/dryioc) C# IoC
* [unit-threaded](https://github.com/atilaneves/unit-threaded) Multi-threaded unit test framework for D.

## License
Distributed under the Boost Software License, Version 1.0.
See copy at http://www.boost.org/LICENSE_1_0.txt.
