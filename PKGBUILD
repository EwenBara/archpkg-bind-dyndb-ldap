# Maintainer: Ewen BARA <ewen.bara+aur@gmail.com>
pkgname=bind-dyndb-ldap
pkgver=11.8
pkgrel=1
pkgdesc='LDAP driver for BIND'
arch=('x86_64')
url=https://pagure.io/bind-dyndb-ldap
license=('GPLv2')
depends=('bind')
makedepends=()
source=(
        "https://releases.pagure.org/bind-dyndb-ldap/$pkgname-$pkgver.tar.bz2"
)
sha512sums=(
        'f7449ee48da30990ec10ae1b2907ffcb542c0a05023cda55c16bbb7d0544b6b9c18495018200cab0b4b7ebb6a721b5acf7ddbb116eee5a1bc2121e4aeda2e5e2'
)

prepare() {
        cd $pkgname-$pkgver
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
