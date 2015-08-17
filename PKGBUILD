# Maintainer: matmoser <matmoser@wu.ac.at>
pkgname=openbugs
pkgver=3.2.3
pkgrel=1
pkgdesc="(Open)BUGS is a software package for performing Bayesian inference Using Gibbs Sampling"
url="http://www.openbugs.info"
arch=('x86_64' 'i686')
license=('GPLv2')
depends=()
optdepends=('R')
makedepends=('gcc-multilib')
provides=('OpenBUGS')
source=("${pkgname}_${pkgver}.tar.gz::http://www.openbugs.net/w/OpenBUGS_3_2_3?action=AttachFile&do=get&target=OpenBUGS-$pkgver.tar.gz")
md5sums=('196253b34ba07886ac9db0c734e31fbf')


build() {
  mv "${srcdir}/OpenBUGS-${pkgver}" "${srcdir}/${pkgname}-${pkgver}"
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  sed -i 's/prefix = \/usr/prefix=${pkgdir}\/usr/' $srcdir/$pkgname-$pkgver/src/Makefile
  make INSTDIR=${pkgdir}/usr/lib/OpenBUGS prefix=${pkgdir}/usr install
}

