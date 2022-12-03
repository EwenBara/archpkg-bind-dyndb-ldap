# Maintainer: Ewen BARA <ewen.bara+aur@gmail.com>
pkgname=bind-dyndb-ldap
pkgver=11.10
pkgrel=2
pkgdesc='LDAP driver for BIND'
arch=('x86_64')
url=https://pagure.io/bind-dyndb-ldap
license=('GPL2')
depends=('bind')
makedepends=()
source=(
        "https://releases.pagure.org/bind-dyndb-ldap/$pkgname-$pkgver.tar.gz"
        "bind-9.18.9.patch"
)
sha512sums=(
        '51e2679488e88e10a77eda4e09c22218f50f2013552cb2a55afabb98b76a6a418ca874066e17bb96f492f92a93120cbf366673d05d593585afb20d5bd4f4033e'
        '92cdf5d4defd3b51b3dae5afb086f9c1f4e84295c455f322c4c23aece25743a6f9b6107a7edc070c273a6c98ead0c11a153ad7bd0fd8d8c8ef0f64fd244008c5'
)

prepare() {
        cd $srcdir/$pkgname-$pkgver
        patch --forward --strip=1 --input="${srcdir}/bind-9.18.9.patch"
}

build() {
        cd $srcdir/$pkgname-$pkgver
        autoreconf -fvi
        ./configure --prefix=/usr --libdir=/usr/lib
        make
}

package() {
        cd $srcdir/$pkgname-$pkgver
        make DESTDIR="$pkgdir" install
}
