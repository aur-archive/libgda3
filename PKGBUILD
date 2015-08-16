# Contributor: Sergej Pupykin <pupykin.s+arch@gmail.com>

pkgname=libgda3
pkgver=3.1.5
pkgrel=11
pkgdesc="Data abstraction layer; with mysql, pgsql, ldap, xml, sqlite providers"
arch=('i686' 'x86_64')
url="http://www.gnome-db.org/Download"
license=('GPL')
depends=('glib2' 'libxslt' 'popt' 'rarian' 'db' 'gnome-vfs'
         'libmysqlclient' 'postgresql-libs>=8.4.1' 'libldap' 'unixodbc' 'sqlite')
makedepends=('intltool' 'pkgconfig' 'gtk-doc' 'util-linux-ng')
options=('!distcc')
source=(http://ftp.acc.umu.se/pub/GNOME/sources/libgda/3.1/libgda-$pkgver.tar.bz2)
md5sums=('eb7da5286a112e7cff3111c89fba4456')

build() {
  cd "${srcdir}"/libgda-$pkgver

  ./configure --prefix=/usr --sysconfdir=/etc
  make
}

package(){
  cd "$srcdir"/libgda-$pkgver

  make DESTDIR="${pkgdir}" install
  cd "${pkgdir}" && find -name \*..so -exec rename '..so' '.a' {} \;
}
