# Maintainer: Masayoshi Wada <developer@andantesoftware.com>

pkgname=st
pkgver=0.9
pkgrel=1
pkgdesc="A simple terminal implementation for X."
arch=("x86_64")
url="https://st.suckless.org"
license=("MIT")
depends=("libxft")
source=("${pkgname}-${pkgver}::https://dl.suckless.org/$pkgname/$pkgname-$pkgver.tar.gz"
        "config.h")
sha256sums=("f36359799734eae785becb374063f0be833cf22f88b4f169cd251b99324e08e7"
            "8c6e61cabdd083315863c77e72ef5f669496b24863c3f1420ce83af3927da53d")

prepare() {
  cp "config.h" "$pkgname-$pkgver/config.h"
}

build() {
	cd "$pkgname-$pkgver"
	make
}

package() {
	cd "$pkgname-$pkgver"
	make PREFIX=/usr DESTDIR="$pkgdir/" install
}
