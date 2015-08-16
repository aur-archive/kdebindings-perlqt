# $Id: PKGBUILD 226426 2014-11-19 16:56:22Z fyan $
# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kdebindings-perlqt
pkgver=4.14.3
pkgrel=1
pkgdesc="Perl bindings for the Qt libraries"
url="https://projects.kde.org/projects/kde/kdebindings/perl/perlqt"
arch=('i686' 'x86_64')
license=('GPL' 'LGPL' 'FDL')
groups=('kdebindings')
depends=('kdebindings-smokeqt' 'perl-list-moreutils')
makedepends=('cmake' 'automoc4' 'kdebindings-smokegen')
source=("http://download.kde.org/stable/${pkgver}/src/perlqt-${pkgver}.tar.xz")
sha1sums=('e17ead493e45fc7c23d72dfc734c40a1d3b7a3ba')

build() {
  mkdir build
  cd build
  cmake ../perlqt-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DKDE4_BUILD_TESTS=OFF \
    -DCMAKE_SKIP_RPATH=ON \
    -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
