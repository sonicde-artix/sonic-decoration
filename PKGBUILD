# Maintainer: artist for Artix Linux

pkgname=sonic-decoration
pkgver=6.6.5
pkgrel=1
_commit="2098fbe9148da2342a0d1fb6420cd1adae635058"
pkgdesc='Plugin based library to create window decorations'
arch=(x86_64)
url="https://github.com/Sonic-DE/$pkgname"
license=(LGPL-2.0-or-later)
depends=(glibc
         ki18n
         libgcc
         qt6-base)
makedepends=(extra-cmake-modules)
groups=(sonicde)
conflicts=(kdecoration)
provides=(kdecoration)
replaces=(kdecoration)
makedepends+=(git)
source=("$pkgname-$pkgver::git+$url.git#commit=$_commit")

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
sha256sums=('aa5b1ff807226298e1be96276fedcebe2e106bfda6c41e01b24abfef5d81e36c')
