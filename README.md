# Diffutils64
Attempt to compile diffutils for Windows x64

## build instructions
original from https://amk1.wordpress.com/2013/04/11/diffutils-for-windows-64-bit/ and tweaked by me

    # apt-get install mingw-w64
    wget http://ftp.gnu.org/gnu/diffutils/diffutils-3.3.tar.xz
    tar xJf diffutils-3.3.tar.xz
    cd diffutils-3.3
    patch -p1 -i diffutils-w64.patch
    # fix with the "bonus patch" and then restart here
    ./configure --host=x86_64-w64-mingw32 --prefix=/tmp/diffutils-3.3-mingw64 CFLAGS="-static"
    make
    # don't make check, at least not in MSYS...will fail.
    make install

## "bonus patch"

The "bonus patch" I found from doing some crazy Googling.  I just manually made the update, though, rather than using a patch file

http://git.savannah.gnu.org/gitweb/?p=gnulib.git;a=blobdiff_plain;f=lib/msvc-inval.c;h=1873e23be4c9d46d95a8b7bea7ea5a07db430829;hp=ef2b8609446ec45000d5f08731400111e4f28d16;hb=86725346a1b116f3c2da26c124288f5f4495bf69;hpb=2845ecc459a4ad03de8397a2c942c2e91d2d3ed5

## proof this is 64-bit versions

Got this from my MSYS console after make install

    $ file diff.exe
    diff.exe: PE32+ executable for MS Windows (console) Mono/.Net assembly
