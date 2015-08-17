# $Id$
# Maintainer: Andrzej Giniewicz <gginiu@gmail.com>
# Contributor: Sebastien Binet <binet@lblbox>

pkgname=python2-numexpr
pkgver=2.0.1
pkgrel=1
pkgdesc="A JIT compiler for Python expressions"
url="http://code.google.com/p/numexpr/"
arch=('i686' 'x86_64')
license=('MIT')
depends=('python2-numpy')
makedepends=('python2-distribute')
source=(http://numexpr.googlecode.com/files/numexpr-$pkgver.tar.gz)
md5sums=('5cdc05c2ef8761daeae8a3182e468ba4')

build() {
  cd "$srcdir"/numexpr-$pkgver

  python2 setup.py build
}

package() {
  cd "$srcdir"/numexpr-$pkgver

  python2 setup.py install --prefix=/usr --root="$pkgdir" --optimize=1

  sed -i -e "s|#![ ]*/usr/bin/env python$|#!/usr/bin/python2|" \
    $(find "${pkgdir}" -name '*.py')

  install -Dm644 LICENSE.txt "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}

