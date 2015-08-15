# Maintainer: André van Delden <andre.van.deldenX@Xuni-bremen.de>

pkgname=gqr
pkgver=1500
pkgrel=1

pkgdesc="A solver for binary qualitative constraint networks. GQR takes a calculus description and one or more constraint networks as input, and tries to solve the networks using path consistency and backtracking."

url="http://sfbtr8.informatik.uni-freiburg.de/R4LogoSpace/Tools/gqr.html"
arch=('i686' 'x86_64')
license='GNU GPL'
makedepends=('python2' 'gcc>=4.3.3')
source=('http://sfbtr8.informatik.uni-freiburg.de/R4LogoSpace/downloads/gqr-1500.tar.bz2')
sha512sums=('e73d64988b3f88e926e8e8f655887cc13d7f37f772563555907032b969e5118f9a43c320514e97e6808516388a4c7a29db50e25f9ddb87293ce387d9a270bb69')

prepare() {
  cd ${srcdir}/gqr-${pkgver}
  sed -i '1s/python/python2/' waf wscript
}

build() {
  cd ${srcdir}/gqr-${pkgver}
  ./waf configure || exit 1
  ./waf || exit 1
}

package() {
  cd ${srcdir}/gqr-${pkgver}
  ./waf --destdir="${pkgdir}/" install
}
# vim:syntax=sh
