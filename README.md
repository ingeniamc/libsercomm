# Libsercomm - A Multiplatform Serial Communications Library

`libsercomm` is a portable, pure C implementation library for serial
communications.

`libsercomm` is licensed under a **very permissive license** (GPLv2 with a
special Linking Exception). This basically means that you can link it
(unmodified) with any kind of software without having to release its source
code.

## What It Can Do

The library provides:

* access to serial port (r/w)
* serial ports discovery
* serial ports monitor (be notified when a new serial port is plugged or
  unplugged)
* descriptive and detailed error messages

## Building libsercomm

The `libsercomm` library is built using [CMake](<https://cmake.org/>) (version
3.0 or newer) on all platforms.

Under Unix-like systems, `libsercomm` expects `pthreads` to be available (they
should be installed by default). On Linux, `libudev` is also required for device
listing/monitoring support.

On most systems you can build the library using the following commands:

```sh
cmake -H. -Bbuild
cmake --build build
```

### Build options

The following build options are available:

- `WITH_EXAMPLES` (OFF): When enabled, the library usage example applications
  will be built.
- `WITH_DOCS` (OFF): When enabled the API documentation will be built.
- `WITH_ERRDESC` (ON): When enabled, error details description can be obtained.
- `WITH_GITINFO` (OFF): When enabled, the current Git commit hash will be
  included in version. This may be useful to trace installed development builds.
- `WITH_DEVMON` (ON): When enabled, device listing and monitoring will be
  supported.

Furthermore, *standard* CMake build options can be used. You may find useful to
read this list of [useful CMake variables][cmakeuseful].

[cmakeuseful]: https://cmake.org/Wiki/CMake_Useful_Variables

## Standards Compliance

The public API of `libsercomm` is [ANSI C][ansic] (C89) compatible (fixed
integers required). Internally, `libsercomm` is written in C99.

[ansic]: http://en.wikipedia.org/wiki/ANSI_C