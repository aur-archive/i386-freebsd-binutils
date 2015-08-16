pkgname=i386-freebsd-binutils
pkgver=2.23.1
pkgrel=1
pkgdesc="A set of programs to assemble and manipulate binary and object files (i386 FreeBSD)"
arch=(i686 x86_64)
url="http://www.gnu.org/software/binutils"
license=("GPL")
depends=(glibc)
source=("ftp://ftp.gnu.org/gnu/binutils/binutils-$pkgver.tar.gz")
md5sums=('7a519f12859baa0282866b8e8a4d04f0')

build() {
  cd "${srcdir}/binutils-$pkgver"
  ./configure \
    --prefix=/usr \
    --target=i386-freebsd \
    --host=$CHOST \
    --build=$CHOST \
    --disable-nls
  make
}

package()
{
  cd "${srcdir}/binutils-$pkgver"
  make DESTDIR=$pkgdir install
  rm -rf "$pkgdir/usr/lib"
  rm -rf "$pkgdir/usr/share/"{info,man}
}