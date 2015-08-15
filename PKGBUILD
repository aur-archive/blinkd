pkgname=blinkd
pkgver=0.4.7
pkgrel=3
pkgdesc="A client/server pair that lets the keyboard LEDs blink."
arch=(i686 x86_64)
url="http://www.nongnu.org/blinkd/"
license=('GNU')
install=${pkgname}.install
source=(https://launchpad.net/ubuntu/+archive/primary/+files/${pkgname}_${pkgver}.orig.tar.gz)


md5sums=('ac938c627238e821112d945adac9979e')

https://launchpad.net/ubuntu/+source/blinkd/0.4.7-1.1/+build/110711/+files/blinkd_0.4.7-1.1_i386.deb


build() {
  cd $startdir/src/${pkgname}-${pkgver}
  ./configure
  sed -i 's/@GT_/\t@GT_/g' $srcdir/${pkgname}-${pkgver}/intl/Makefile
  make || return 1
  mkdir -p "$pkgdir/usr/bin"
  mkdir -p "$pkgdir/usr/sbin"
  mkdir -p "$pkgdir/usr/share/doc/blinkd/examples"
  mkdir -p "$pkgdir/usr/share/man/man1"
  mkdir -p "$pkgdir/usr/share/man/man8"
  install -D $srcdir/${pkgname}-${pkgver}/blink $pkgdir/usr/bin/
  install -D $srcdir/${pkgname}-${pkgver}/blinkd $pkgdir/usr/sbin/
  install -D $srcdir/${pkgname}-${pkgver}/README NEWS COPYING ChangeLog AUTHORS $pkgdir/usr/share/doc/blinkd/
  install -d $srcdir/${pkgname}-${pkgver}/examples $pkgdir/usr/share/doc/blinkd/
  install -D $srcdir/${pkgname}-${pkgver}/blink.1 $pkgdir/usr/share/man/man1/
  install -D $srcdir/${pkgname}-${pkgver}/blinkd.8 $pkgdir/usr/share/man/man8/
}
