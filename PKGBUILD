# Contributor: noonov <noonov@gmail.com>

pkgname=fbterm
pkgver=1.7.0
pkgrel=4
pkgdesc="A fast terminal emulator for linux with frame buffer device or VESA video card"
arch=('i686' 'x86_64')
url="http://code.google.com/p/fbterm/"
license=('GPL2')
depends=('gcc-libs' 'fontconfig')
optdepends=('libx86: for VESA video card support')
install=fbterm.install
source=(http://fbterm.googlecode.com/files/${pkgname}-${pkgver}.tar.gz)

build() {
  cd ${srcdir}/${pkgname}-${pkgver%.?}

  ./configure --prefix=/usr
  make
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver%.?}

  install -D -m644 terminfo/fbterm ${pkgdir}/usr/share/terminfo/f/fbterm

  make DESTDIR=${pkgdir} TERMINFO=${pkgdir}/usr/share/terminfo install
}

md5sums=('c36bae75a450df0519b4527cccaf7572')
