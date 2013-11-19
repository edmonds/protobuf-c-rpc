## Overview

This is `protobuf-c-rpc`, a library for performing RPC with `protobuf-c`. It was formerly integrated into the main `protobuf-c` distribution but has now been split out.

## Building

`protobuf-c-rpc` requires a C compiler, [protobuf-c](https://github.com/protobuf-c/protobuf-c), and `pkg-config` to be installed.

    ./configure && make && make install

If building from a git checkout, the `autotools` (`autoconf`, `automake`, `libtool`) must also be installed, and the build system must be generated by running the `autogen.sh` script.

    ./autogen.sh && ./configure && make && make install

## Contributing

Please send patches to the [protobuf-c mailing list](https://groups.google.com/forum/#!forum/protobuf-c) or by opening a GitHub pull request.

Copyright to all contributions are retained by the original author, but must be licensed under the terms of the [BSD-2-Clause](http://opensource.org/licenses/BSD-2-Clause) license. Please add a `Signed-off-by` header to your commit message (`git commit -s`) to indicate that you are licensing your contribution under these terms.
