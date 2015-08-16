# Maintainer: Jeremy M. <jskier@gmail.com>
# Contributor: David Souther <davidsouther@gmail.com>

pkgname=log2timeline
pkgver=0.65
pkgrel=4
pkgdesc="Legacy log2timeline Perl framework for automatic creation of a super timeline, succeeded by plaso"
arch=('any')
url="https://code.google.com/p/log2timeline/"
depends=('perl' 'perl-datetime' 'perl-net-pcap' 'perl-archive-zip' 'perl-html-scrubber' 'perl-exiftool' 'glib-perl' 'perl-libwww' 'pango-perl' 'cairo-perl' 'perl-extutils-pkgconfig' 'perl-extutils-depends' 'perl-netpacket' 'perl-xml-libxml' 'perl-parse-win32registry' 'perl-date-manip' 'perl-datetime-format-strptime' 'perl-dbi' 'perl-file-mork' 'perl-mac-propertylist' 'perl-xml-entities')
source=(http://$pkgname.googlecode.com/files/${pkgname}_${pkgver}.tgz)
license=('GPL')
md5sums=('77e4191e295937edf81c9ceb2ed06897')
provides=('log2timeline')
conflicts=('plaso')

build()
{
	cd log2timeline_${pkgver}
	perl Makefile.PL PREFIX="${pkgdir}"
	make DESTDIR="${pkgdir}"
}

package()
{
	cd log2timeline_${pkgver}
	make install
	cd ${pkgdir}
	pwd
	mkdir usr
	mv share usr/share
	mv lib usr/lib
	mkdir usr/bin
	mv bin/site_perl/* usr/bin/
}
