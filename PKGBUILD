# Maintainer: Ewen BARA <ewen.bara+aur@gmail.com>
pkgname=bind-dyndb-ldap
pkgver=11.10
pkgrel=1
pkgdesc='LDAP driver for BIND'
arch=('x86_64')
url=https://pagure.io/bind-dyndb-ldap
license=('GPL2')
depends=('bind')
makedepends=()
source=(
        "https://releases.pagure.org/bind-dyndb-ldap/$pkgname-$pkgver.tar.bz2"
)
sha512sums=(
        'e8887c450375c2cda062bc6f08eee6505a784dc4f49ba69ba2f46d8d3e1ff3b94adabbcb3ffb978b3b138829d26bfde47d32f35707ca9ecbd0480b59a0e0d964'
)

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
