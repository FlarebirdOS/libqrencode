pkgname=libqrencode
pkgver=4.1.1
pkgrel=2
pkgdesc="C library for encoding data in a QR Code symbol."
arch=('x86_64')
url="https://fukuchi.org/works/qrencode/"
license=('LGPL-2.1-or-later')
depends=('libpng')
makedepends=(
    'git'
    'sdl2'
)
source=(git+ssh://git@github.com/fukuchi/libqrencode#tag=v${pkgver})
sha256sums=(0151f34aa6996aefb0a3d011ce050bf32c70c5644055d8c82dcaa8044332ad35)

prepare() {
    cd ${pkgname}

    autoreconf -fi
}

build() {
    cd ${pkgname}

    local configure_args=(
        ${configure_options}
    )

    ./configure "${configure_args[@]}"

    make
}

package() {
    cd ${pkgname}

    make DESTDIR=${pkgdir} install
}
