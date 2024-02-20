# Maintainer: Aldo Adirajasa Fathoni <aldo.alfathoni@gmail.com>

pkgname=whatsie-git
pkgver=4.14.2.r1.g3092158
pkgrel=1
pkgdesc="Fast Light weight WhatsApp Client based on Qt's WebEngine, With lots of settings and packed goodies"
arch=('armel' 'armhf' 'arm64' 'i386' 'amd64')
url="https://github.com/keshavbhatt/whatsie"
license=('MIT')
depends=('libqt5widgets5' 'libqt5quickwidgets5' 'libqt5location5' 'libqt5webchannel5' 'libqt5webengine5' 'libqt5webenginewidgets5')
makedepends=('git' 'qtbase5-dev' 'qtdeclarative5-dev' 'qtlocation5-dev' 'libqt5webchannel5-dev' 'qtwebengine5-dev' 'qtwebengine5-dev-tools')
conflicts=("${pkgname%-git}")
provides=("${pkgname%-git}")
source=("${pkgname%-git}::git+${url}")
sha256sums=('SKIP')

pkgver() {
  cd "${pkgname%-git}"

  printf "%s" "$(git describe --long --tags | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g')"
}

build() {
  cd "${pkgname%-git}"
  qmake src
  make
}

package() {
  cd "${pkgname%-git}"
  make INSTALL_ROOT="${pkgdir}" install
}
