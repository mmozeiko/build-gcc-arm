Automatic Windows build of [gcc][] compiler, [gdb][] debugger and [make][] for targeting 32-bit and 64-bit arm bare-metal targets.

Download 64-bit Windows binary build as 7z archive from [latest release][] page.

To build binaries locally run `build.sh`. Make sure you have installed all necessary dependencies.

To build binaries using Docker, run:

    docker run -ti --rm -v `pwd`:/output -e OUTPUT=/output -w /mnt ubuntu:24.04
    apt update
    DEBIAN_FRONTEND=noninteractive apt install --no-install-recommends -y \
        ca-certificates libgmp-dev libmpc-dev libmpfr-dev libisl-dev xz-utils texinfo patch bzip2 p7zip cmake make curl m4 gcc g++ mingw-w64
    /output/build.sh 32
    /output/build.sh 64
    exit

[gcc]: https://gcc.gnu.org/
[gdb]: https://www.gnu.org/software/gdb/
[make]: https://www.gnu.org/software/make/
[latest release]: https://github.com/mmozeiko/build-gcc-arm/releases/latest
