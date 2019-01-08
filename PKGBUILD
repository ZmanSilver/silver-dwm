# Maintainer:  Zachary Silver <zmansilver@gmail.com>

pkgname=silver-dwm
pkgver=6.1
pkgrel=4
pkgdesc="A customized clone of a dynamic window manager for X"
url="https://github.com/ZmanSilver/silver-dwm"
arch=('i686' 'x86_64')
license=('MIT')
options=(zipman)
depends=('libx11' 'libxinerama' 'libxft' 'freetype2' 'ttf-font-awesome')
optdepends=('st: terminal emulator'
	    'silver-st: customized terminal emulator'
	    'dmenu: application launcher'
	    'silver-dmenu: customized application launcher')
provides=($pkgname)
conflicts=($pkgname 'dwm')
install=dwm.install
source=(https://www.dropbox.com/s/48iuaj9jdzd97eb/silver-dwm.tar.gz
	config.h
	dwm.desktop)
md5sums=('933b78e8ed497cdc39956ac3b20240b4'
         'e69c18bb1d8219f186314d8de95f80e1'
         '7f873efd596b8b30e2cdc09583209874')

prepare() {
  cd $srcdir/$pkgname
  cp $srcdir/config.h config.h
}

build() {
  cd $srcdir/$pkgname
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 FREETYPEINC=/usr/include/freetype2
}

package() {
  cd $srcdir/$pkgname
  make PREFIX=/usr DESTDIR=$pkgdir install
  install -m644 -D LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
  install -m644 -D README $pkgdir/usr/share/doc/$pkgname/README
  install -m644 -D $srcdir/dwm.desktop $pkgdir/usr/share/xsessions/dwm.desktop
}
