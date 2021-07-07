# Maintainer: Jonas Strassel <info@jonas-strassel.de>
# Maintainer: Simon Büeler <simon.bueeler at icloud dot com>

pkgname="swaylock-effects"
_minor=1.6
_patch=3
_sourcever=$_minor-$_patch
pkgver=r95.acf3319
pkgrel=2
pkgdesc="A fancier screen locker for Wayland."
arch=('i686' 'x86_64')
url="https://github.com/mortie/$pkgname"
license=('MIT')
depends=('libxkbcommon' 'cairo' 'gdk-pixbuf2' 'pam')
makedepends=('git' 'meson' 'ninja' 'scdoc' 'cmake' 'wayland' 'wayland-protocols')
provides=('swaylock' 'swaylock-effects')
conflicts=('swaylock')
source=("$pkgname.tar.gz::$url/archive/v$_sourcever.tar.gz")
md5sums=('46b454bebe633abc9627a916a1c12544')

build() {
	cd "$srcdir/$pkgname-$_sourcever"
	meson build --prefix=/usr
	ninja -C build
}

package() {
	cd "$srcdir/$pkgname-$_sourcever"
	DESTDIR="$pkgdir" ninja -C build install
}
