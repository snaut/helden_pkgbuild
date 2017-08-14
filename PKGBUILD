pkgname=helden
pkgver=5.5.3
pkgrel=1
pkgdesc='Die Heldenverwaltung für das Pen&Paper-Rollenspiel "Das Schwarze Auge" (DSA)'
arch=('any')
url="http://www.helden-software.de"
license=('custom')
depends=('java-environment' 'bash')
makedepends=('gendesk')
source=("http://www.helden-software.de/down/hs5/050503/helden.jar" "helden.png" "helden.sh")
noextract=("helden.jar")
sha256sums=('3f46eefaed177f09d79178b822507275b2b5c91a474bc9c379ae0e82ed4fecf6' 'b7be569d7d26618e6798c0f528b6ba4858d066e5bdf7c1bfbf5d4198c713aec5' 'b5312b060d113d0121acac3d5c3a1c96fbf465b1a62e7fa83f3f7c3f3318a723')
_exec=/usr/bin/helden
_name=Helden


prepare() {
  # create .desktop file
  gendesk -n --pkgname "$pkgname" --pkgdesc "$pkgdesc"
}

package() {

  # install jar file
  install -Dm755 "$pkgname.jar" "$pkgdir/usr/share/java/$pkgname/$pkgname.jar"

  # install launcher shellscript
  install -Dm755 "$pkgname.sh" "$pkgdir/usr/bin/$pkgname"

  # install .desktop file and icon
  install -Dm644 "$pkgname.desktop" "$pkgdir/usr/share/applications/$pkgname.desktop"
  install -Dm644 "$pkgname.png" "$pkgdir/usr/share/pixmaps/$pkgname.png"
}
