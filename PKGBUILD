# Maintainer: Andrzej Giniewicz <gginiu@gmail.com>
pkgname=cloud
pkgver=2.6.8
pkgrel=1
pkgdesc="Client-side module to connect to the PiCloud servers"
arch=(any)
url="http://www.picloud.com/"
license=('LGPL')
depends=('python2')
makedepends=('python2-distribute')
install="cloud.install"
options=(!emptydirs)
source=(http://s3.amazonaws.com/cloud_download/cloud-$pkgver.tar.gz)
md5sums=('fa2eb925a76fb99e048515122df99b15')

build() {
  cd "$srcdir"/${pkgname}-$pkgver
  python2 setup.py build
}

package() {
  cd "$srcdir"/${pkgname}-$pkgver
  python2 setup.py install --root="$pkgdir"/ --optimize=1
  sed -i -e "s|#![ ]*/usr/bin/python$|#!/usr/bin/python2|" \
         -e "s|#![ ]*/usr/bin/env python$|#!/usr/bin/env python2|" \
    $(find "${pkgdir}" -name '*.py')
}

