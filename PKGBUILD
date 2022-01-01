# Maintainer: Jonas Strassel <info@jonas-strassel.de>
# Maintainer: Simon Büeler <simon.bueeler at icloud dot com>

pkgname="swaylock-effects"
_sourcever="a8fc557b86e70f2f7a30ca9ff9b3124f89e7f204"
pkgver=1.6.3
pkgrel=4
pkgdesc="A fancier screen locker for Wayland."
arch=('aarch64' 'x86_64')
url="https://github.com/mortie/$pkgname"
license=('MIT')
depends=('libxkbcommon' 'cairo' 'gdk-pixbuf2' 'pam')
makedepends=('git' 'meson' 'ninja' 'scdoc' 'cmake' 'wayland' 'wayland-protocols')
provides=('swaylock' 'swaylock-effects')
conflicts=('swaylock')
source=("$pkgname.tar.gz::$url/archive/$_sourcever.tar.gz")
md5sums=('bdc48f92d1ab1900d0e0e33fe784a013')

build() {
	cd "$srcdir/$pkgname-$_sourcever"
	meson build --prefix=/usr
	ninja -C build
}

package() {
	cd "$srcdir/$pkgname-$_sourcever"
	DESTDIR="$pkgdir" ninja -C build install
}
