# Contributor: Loui Chang <louipc dot ist at gmail company>

pkgname=spong
pkgver=0.0.1
pkgrel=1
pkgdesc="A rudimentary version of the old pong game."
url="http://louipc.github.io/spong"
license=('GPL')
arch=('i686' 'x86_64')
depends=(sdl)
source=(http://louipc.github.io/spong/files/spong-0.0.1.tar.gz
http://louipc.github.io/spong/files/001-spong-0.0.1-Change-image-path.patch)
md5sums=('e43f51feb7d4fdb4cd0b435667bfb215'
         'd3125533b2cd35dfa1ad375cd6c23b95')

build() {
	cd $srcdir/$pkgname-$pkgver
	patch -p1 < ../001-spong-0.0.1-Change-image-path.patch
	make || return
}

package() {
	cd $srcdir/$pkgname-$pkgver
	install -D -m755 spong $pkgdir/usr/bin/spong
	install -d $pkgdir/usr/share/spong/img
	install -D -m644 img/* $pkgdir/usr/share/spong/img
	install -D -m644 README $pkgdir/usr/share/spong/
}

