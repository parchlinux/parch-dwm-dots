
pkgname=parch-dwm-dots
pkgver=6.3
pkgrel=1
pkgdesc="Parch Linux dwm config."
arch=(x86_64)
url="https://github.com/parchlinux/parch-dwm-dots"
license=('MIT')
groups=()
depends=(libx11 libxinerama ttf-hack ttf-joypixels freetype2 kitty dmenu )
makedepends=(make)
checkdepends=()
optdepends=(surf)
provides=(dwm)
conflicts=(dwm)
replaces=()
backup=()
options=()
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()


build() {
  cd parch-dwm-dots
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 FREETYPEINC=/usr/include/freetype2
}

package() {
  cd parch-dwm-dots  
  mkdir -p ${pkgdir}/opt/${pkgname}
  cp -rf * ${pkgdir}/opt/${pkgname}
  make PREFIX=/usr DESTDIR="${pkgdir}" install
  install -Dm644 "${srcdir}/parch-dwm-dots/dwm.desktop" "$pkgdir/usr/share/xsessions/dwm.desktop"
}

