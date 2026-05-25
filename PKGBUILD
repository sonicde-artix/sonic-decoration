# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-decoration
pkgver=6.6.5
pkgrel=2
pkgdesc='Plugin based library to create window decorations'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-decoration'
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
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('04c0560b9a159872cdeadb1f8840300a5403964ec32d27d00c9f85022110da1f')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
