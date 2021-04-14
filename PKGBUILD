# Maintainer: Ewen BARA <ewen.bara+aur@gmail.com>
pkgname=bind-dyndb-ldap
pkgver=11.6
pkgrel=4
pkgdesc='LDAP driver for BIND'
arch=('x86_64')
url=https://pagure.io/bind-dyndb-ldap
license=('GPLv2')
depends=('bind=9.16.11')
makedepends=()
source=(
        "https://releases.pagure.org/bind-dyndb-ldap/$pkgname-$pkgver.tar.bz2"
        "bind-9.16.9.patch"
        "bind-9.16.10.patch"
        "bind-9.16.11.patch"
)
sha512sums=(
        '501a78e07e3840fba64eb9f6c5be204d2e6166874a6b993611ce40b81fa468d13bd517dea663488e974bec6b8cee789e5cc7032120b2473b8adaa176d1fd0f31'
        '435726608ca7e97a1bdf3fc7dbab0b3200f2f502864cbdb00c14a173ad5032fec1e0ddd9a814090d301ed1ba2d8f414551887d328bfda54196deed7550cbd3e6'
        'ca905dbe0e3d1cd7d88be4213224aa5a30c239b4dc0c60b5f968b5053992650123562f452b6eaf536ef74bd2a7656049d0d9fc7408d505d872489129cf5d4c0a'
        '9b0ed7fc195f0f130cb6892d3d7264dbb97047666564b226a6283d0f07ce8888cc1d20422093b459f495900654169e4e65a8d19fc97f666e615a6fd87c52a50a'
)

prepare() {
        cd $pkgname-$pkgver
        patch --forward --strip=1 --input="${srcdir}/bind-9.16.9.patch"
        patch --forward --strip=1 --input="${srcdir}/bind-9.16.10.patch"
        patch --forward --strip=1 --input="${srcdir}/bind-9.16.11.patch"
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
