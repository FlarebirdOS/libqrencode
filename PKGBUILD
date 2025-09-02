pkgname=libqrencode
pkgver=4.1.1
pkgrel=1
pkgdesc="C library for encoding data in a QR Code symbol."
arch=('x86_64')
url="https://fukuchi.org/works/qrencode"
license=('LGPL-2.1-or-later')
depends=('libpng')
source=(https://github.com/fukuchi/libqrencode/archive/v${pkgver}/${pkgname}-${pkgver}.tar.gz)
sha256sums=(5385bc1b8c2f20f3b91d258bf8ccc8cf62023935df2d2676b5b67049f31a049c)

prepare() {
    cd ${pkgname}-${pkgver}

    sh autogen.sh
}

build() {
    cd ${pkgname}-${pkgver}

    local configure_args=(
        ${configure_options}
    )

    ./configure "${configure_args[@]}"

    make
}

package() {
    cd ${pkgname}-${pkgver}

    make DESTDIR=${pkgdir} install
}
