# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kprintutils
pkgver=4.96.0
pkgrel=1
pkgdesc='KPrintUtils'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kprintutils'
license=('LGPL')
depends=('kparts')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('95b0ff7563d36b9d31e205d40003bfc4')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
