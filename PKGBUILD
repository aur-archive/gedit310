# Maintainer Levi Nachmani (levi0x0)
# Contributor: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Jan de Groot <jgc@archlinux.org>

pkgname=gedit310
pkgver=3.10.4
pkgrel=1
pkgdesc="A text editor for GNOME"
arch=(i686 x86_64)
license=(GPL)
depends=(gtksourceview3 gsettings-desktop-schemas libpeas enchant iso-codes desktop-file-utils python-gobject dconf)
makedepends=(yelp-tools intltool zeitgeist vala)
optdepends=('zeitgeist: Zeitgeist plugin')
#groups=(gnome-extra)
conflicts=(gedit)
options=('!emptydirs')
url="http://www.gnome.org"
install=gedit.install
source=(http://ftp.gnome.org/pub/gnome/sources/gedit/3.10/gedit-3.10.4.tar.xz)
md5sums=('62f9e61297487bcd2ea21ec229e8e284')

build() {
  cd gedit-$pkgver
  ./configure --prefix=/usr \
      --sysconfdir=/etc --localstatedir=/var \
      --libexecdir=/usr/lib --disable-updater --disable-schemas-compile \
      --enable-python
  make
}

package(){
  cd gedit-$pkgver
  make DESTDIR="$pkgdir" install
}
