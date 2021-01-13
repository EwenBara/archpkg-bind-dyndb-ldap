pkgname=bind-dyndb-ldap
pkgver=11.6
pkgrel=2
pkgdesc='LDAP driver for BIND'
arch=('x86_64')
url=https://pagure.io/bind-dyndb-ldap
license=('GPLv2')
depends=('bind')
makedepends=()
source=(
        "https://releases.pagure.org/bind-dyndb-ldap/$pkgname-$pkgver.tar.bz2"
        "bind-9.16.9.patch"
        "bind-9.16.10.patch"
)
sha512sums=(
        'e44ee7870aec9304c3d553181392ee2dca38352620bab2f78405aa714a60434990db7fce3a0f1db457257e68bf10fc8a7c23328aee67e7bd5dcda4b8aa67e08c'
        '435726608ca7e97a1bdf3fc7dbab0b3200f2f502864cbdb00c14a173ad5032fec1e0ddd9a814090d301ed1ba2d8f414551887d328bfda54196deed7550cbd3e6'
        'ca905dbe0e3d1cd7d88be4213224aa5a30c239b4dc0c60b5f968b5053992650123562f452b6eaf536ef74bd2a7656049d0d9fc7408d505d872489129cf5d4c0a'
)

prepare() {
        cd $pkgname-$pkgver
        patch --forward --strip=1 --input="${srcdir}/bind-9.16.9.patch"
}

build() {
        cd $srcdir/$pkgname-$pkgver
        autoreconf -fvi
        ./configure --prefix=/usr
        make
}

package() {
        cd $srcdir/$pkgname-$pkgver
        make DESTDIR="$pkgdir" install
}
