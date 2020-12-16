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
sha512sums=('83bbf7ccb1a47c7c9eb18bdb5310c33a117b4445483b1a8b84c36d01482c53ea102a23b9826b14148a4634d934f45998d6dd3cd58aac5b576628f43409d26396')

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
