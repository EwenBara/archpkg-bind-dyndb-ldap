pkgname=bind-dyndb-ldap
pkgver=11.6
pkgrel=1
pkgdesc='LDAP driver for BIND'
arch=('x86_64')
url=https://pagure.io/bind-dyndb-ldap
license=('GPLv2')
depends=('bind')
makedepends=()
source=("https://releases.pagure.org/bind-dyndb-ldap/$pkgname-$pkgver.tar.bz2")
sha512sums=('51063f5d33f41b125feb5379668503bdfcc444bc463e661a390fda4ed6bc801f0771b32b84878091d987cf893bb5a6287f70e794cf7940161677e49d7c945377')

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
