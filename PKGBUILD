# Contributer: BeholdMyGlory <larvid@gmail.com>
pkgname=mupen64plus-rsp-z64-hg
pkgver=67
pkgrel=1
pkgdesc="Low-level RSP processor plugin for Mupen64Plus v2.0, a Nintendo 64 emulator. Latest hg pull."
url="http://bitbucket.org/wahrhaft/mupen64plus-rsp-z64"
license=("GPL")
arch=(i686 x86_64)
groups=(mupen64plus-hg)
depends=(mupen64plus-core-hg)
makedepends=(mercurial)
source=("hg+https://bitbucket.org/wahrhaft/mupen64plus-rsp-z64")
md5sums=('SKIP')

pkgver() {
	cd $srcdir/${pkgname%-*}
	echo $(hg identify -n)
}

build() {
	cd "${srcdir}/${pkgname%-*}"
	make -C projects/unix all
}

package() {
	cd "${srcdir}/${pkgname%-*}"
	make -C projects/unix PREFIX=/usr DESTDIR=${pkgdir} install
}
