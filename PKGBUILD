pkgbase=python-recommonmark
pkgname=('python-recommonmark' 'python2-recommonmark')
pkgver=0.4.0
pkgrel=1
pkgdesc="A markdown parser for docutils"
url="https://github.com/rtfd/recommonmark"
arch=(any)
license=('MIT')
makedepends=('python-setuptools' 'python2-setuptools')
source=("https://pypi.python.org/packages/source/r/recommonmark/recommonmark-${pkgver}.tar.gz")
md5sums=('f8e9d96ab19922652c4e35d73155967e')

build() {
  cp -r "${srcdir}"/recommonmark-$pkgver "${srcdir}"/recommonmark-$pkgver-py2

  cd "${srcdir}"/recommonmark-$pkgver
  python setup.py build

  cd "${srcdir}"/recommonmark-$pkgver-py2
  python2 setup.py build
}

package_python-recommonmark() {
  depends=('python-docutils')

  cd "${srcdir}/recommonmark-$pkgver"
  python setup.py install --root=${pkgdir}
}

package_python2-recommonmark() {
  depends=('python2-docutils')

  cd "${srcdir}/recommonmark-$pkgver"
  python2 setup.py install --root=${pkgdir}
}

