# Contributor: Timur Antipin < kosmocap (at) gmail.com >
# Contributor: Alexey Ivanov < alexey.ivanes (at) gmail.com >
# Contributor: Aliaksandr Stelmachonak < mail (at) ava1ar (dot) info  >

pkgname=vacuum-svn
pkgver=2373
pkgrel=1
pkgdesc='Cross-platform Qt-based jabber client'
arch=('i686' 'x86_64')
url="http://code.google.com/p/vacuum-im/"
license=('GPL3')
conflicts=('vacuum')
provides=('vacuum')
replaces=('vacuum')
depends=('qt4>=4.7.4' 'openssl' 'libidn' 'zlib' 'libxss' 'qtwebkit' 'enchant')
makedepends=('subversion' 'cmake')
source=('svn+http://vacuum-im.googlecode.com/svn/trunk')
md5sums=('SKIP')

pkgver() {
  cd ${srcdir}/trunk
  svnversion | tr -d [A-z]
}

build() {
  cd ${srcdir}
  mkdir -p ${pkgname}-build
  cd ${pkgname}-build
  cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release ../trunk
  make
}

package() {
  cd ${srcdir}/${pkgname}-build
  make DESTDIR=${pkgdir} install
  rm -rf ${srcdir}/${pkgname}-build
} 
