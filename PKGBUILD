# Maintainer: Maxime Gauduin <alucryd@archlinux.org>

pkgname=switchboard-plug-locale
pkgver=0.2
pkgrel=1
pkgdesc='Locale plug for Switchboard'
arch=('i686' 'x86_64')
url='https://launchpad.net/switchboard-plug-locale'
license=('GPL3')
depends=('accountsservice' 'glib2' 'glibc' 'gnome-desktop' 'gtk3' 'ibus'
         'libgee' 'polkit'
         'libgranite.so' 'libswitchboard-2.0.so')
makedepends=('cmake' 'vala')
install='switchboard-plug-locale.install'
source=("https://launchpad.net/switchboard-plug-locale/freya/${pkgver}/+download/switchboard-plug-locale-${pkgver}.tar.xz")
sha256sums=('d009f33b9fe3afe6c0821fd98ad2be510b40fd7cc398a3a0ed786dd4491cc6da')

prepare() {
  cd switchboard-plug-locale-${pkgver}

  if [[ -d build ]]; then
    rm -rf build
  fi
  mkdir build
}

build() {
  cd switchboard-plug-locale-${pkgver}/build

  cmake .. \
    -DCMAKE_BUILD_TYPE='Release' \
    -DCMAKE_INSTALL_PREFIX='/usr' \
    -DCMAKE_INSTALL_LIBDIR='/usr/lib'
  make
}

package() {
  cd switchboard-plug-locale-${pkgver}/build

  make DESTDIR="${pkgdir}" install
}

# vim: ts=2 sw=2 et:
