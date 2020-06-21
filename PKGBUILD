# Maintainer: toshi75 <XXXXX@gmail.com>
#
# Not match "Arch package guidelines".
#  "Packages should never be installed to /usr/local/"
#
pkgname=tonido-server-bin
_pkgname=tonido
pkgver=14.90.0.34042
pkgrel=1
pkgdesc="tonido server, official binary."
arch=('x86_64')
url="http://www.tonido.com"
license=('freeware')
depends=('libpng12')
provides=('tonido')
conflicts=('tonido' 'tonido-server' 'tonido-server-bin')
source=("tonido64.tar.gz::http://www.tonido.com/download.php?tonido64.tar.gz")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir"
  (
    cat manifest.xml |grep \<Version\> |
                      sed -e 's|^.*<Version>||g' \
                          -e 's|<\/Version>||g'
  )
}

package() {
  cd "$srcdir"
  unlink "$srcdir/tonido64.tar.gz"
  files=$(ls -1A)
  mkdir -p "$srcdir/$_pkgname"
  mv $files -t "$srcdir/$_pkgname"
  mkdir -p "$pkgdir/usr/local/tonido"
  mv "$srcdir/$_pkgname" "$pkgdir/usr/local"
}
