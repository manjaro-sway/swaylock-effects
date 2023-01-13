# Maintainer: itsme <mymail@ishere.ru>

pkgname=swaylock-effects
pkgver=1.6.10
_pkgver=cd07dd1082a2fc1093f1e6f2541811e446f4d114
pkgrel=4
pkgdesc="A fancier screen locker for Wayland."
arch=('i686' 'x86_64')
url="https://github.com/jirutka/$pkgname"
license=('MIT')
depends=('libxkbcommon' 'cairo' 'gdk-pixbuf2' 'pam')
makedepends=('git' 'meson' 'ninja' 'scdoc' 'wayland' 'wayland-protocols')
provides=('swaylock' 'swaylock-effects')
conflicts=('swaylock' 'swaylock-effects-git')
source=("https://github.com/jirutka/$pkgname/archive/$_pkgver.tar.gz")
sha256sums=('1f684924483843b2081f1d7e0e12b3080f777c088f660ca3520b7cc4921c2b31')

build() {
	cd "$pkgname-$_pkgver"
	meson build --prefix=/usr
	ninja -C build
}

package() {
	cd "$pkgname-$_pkgver"
	DESTDIR="$pkgdir" ninja -C build install
}
