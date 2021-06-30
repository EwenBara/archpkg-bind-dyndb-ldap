# Maintainer: Ewen BARA <ewen.bara+aur@gmail.com>
pkgname=bind-dyndb-ldap
pkgver=11.9
pkgrel=2
pkgdesc='LDAP driver for BIND'
arch=('x86_64')
url=https://pagure.io/bind-dyndb-ldap
license=('GPLv2')
depends=('bind')
makedepends=()
source=(
        "https://releases.pagure.org/bind-dyndb-ldap/$pkgname-$pkgver.tar.bz2"
        "bind-9.16.17.patch"
)
sha512sums=(
        'e8887c450375c2cda062bc6f08eee6505a784dc4f49ba69ba2f46d8d3e1ff3b94adabbcb3ffb978b3b138829d26bfde47d32f35707ca9ecbd0480b59a0e0d964'
        'b73eb38cacd9725f6bbfa4f7a33fbeaaf7f33fcf67c02dfc50eb90ac38d190fdb0e8352f76b7fc76050f07afa5a137539b1879b535deb3e71e4e581f453e6cdc'
)

prepare() {
        cd $pkgname-$pkgver
        patch --forward --strip=1 --input="${srcdir}/bind-9.16.17.patch"
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
