# Diffutils64
Attempt to compile diffutils for Windows x64

## build instructions
from https://amk1.wordpress.com/2013/04/11/diffutils-for-windows-64-bit/

apt-get install mingw-w64
wget http://ftp.gnu.org/gnu/diffutils/diffutils-3.3.tar.xz
tar xJf diffutils-3.3.tar.xz
cd diffutils-3.3
patch -p1 -i diffutils-3.3-mingw64.patch
./configure --host=x86_64-w64-mingw32 --prefix=/tmp/diffutils-3.3-mingw64
make && make install
