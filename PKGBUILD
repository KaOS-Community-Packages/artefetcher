pkgname=artefetcher
pkgver=0.6.5
pkgrel=1
pkgdesc="A video grabber for Arte Catch UP TV - QT5 version"
arch=('x86_64')
url="http://artefetcher.sourceforge.net/"
license=('GPL')
depends=('qt5-base' 'qt5-script' 'qt5-xmlpatterns' 'libxkbcommon')
makedepends=('qt5-script' 'qt5-webkit' 'qt5-tools')
options=('!libtool' '!emptydirs')
source=(http://downloads.sf.net/sourceforge/${pkgname}/artefetcher_${pkgver}.tar.gz)
sha512sums=('900485e7b948647b860513986edb22c4418ade2f593e0e70a33206590beff4270389b8dd3e10e68990e112240b8ad7c6302c623e3b761af0197546f176a23897')

build() {
  cd ${pkgname}
  lrelease-qt5 arteFetcher_*.ts
  qmake-qt5 PREFIX=${pkgdir}/usr/bin
  make
} 

package() {
   cd ${pkgname}
   mkdir -p "${pkgdir}"/usr/share/applications
   cp arteFetcher.desktop "${pkgdir}"/usr/share/applications
   mkdir -p "${pkgdir}"/usr/share/pixmaps
   cp img/arteFetcher.png "${pkgdir}"/usr/share/pixmaps
   make DESTDIR="${pkgdir}" install 
}
