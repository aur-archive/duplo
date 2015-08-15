# Maintainer: Erico Nunes <nunes dot erico at gmail>
# Contributor: Erico Nunes <nunes dot erico at gmail>

pkgname=duplo
pkgver=0.2.0
pkgrel=2
pkgdesc="C/C++/Java duplicate source code block finder."
arch=(i686 x86_64)
url="http://duplo.sourceforge.net"
license=('GPL')
source=("http://downloads.sourceforge.net/project/${pkgname}/${pkgname}/${pkgname}_${pkgver}/${pkgname}_${pkgver}_src.tar.gz")
md5sums=('1eea4c2b761ee7feab501148cc850392')

prepare() {
	cd "$srcdir/${pkgname}_${pkgver}_src"
	# This version doesn't compile on Linux without <cstring>.
	sed -i '21i#include <cstring>' Duplo.cpp
}

build() {
	cd "$srcdir/${pkgname}_${pkgver}_src"
	make
}

package() {
	cd "$srcdir/${pkgname}_${pkgver}_src"

	mkdir -p "${pkgdir}/usr/bin"
	install -m755 duplo "${pkgdir}/usr/bin"

	mkdir -p "${pkgdir}/usr/share/doc"
	install -m644 COPYING "${pkgdir}/usr/share/doc"
	install -m644 README  "${pkgdir}/usr/share/doc"
}

