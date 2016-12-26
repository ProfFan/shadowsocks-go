# Maintainer: ProfFan

pkgname="shadowsocks-go"
pkgver=1.1.5
pkgrel=2
pkgdesc="go port of shadowsocks. USAGE located at https://github.com/SaberSalv/aur/tree/master/shadowsocks-go"
arch=("x86_64")
url="https://github.com/shadowsocks/shadowsocks-go"
license=("Unkown")
conflicts=("shadowsocks")
provides=("shadowsocks")
source=(
  "https://github.com/shadowsocks/shadowsocks-go/releases/download/${pkgver}/shadowsocks-server-linux64-${pkgver}.gz"
  "https://github.com/shadowsocks/shadowsocks-go/releases/download/${pkgver}/shadowsocks-local-linux64-${pkgver}.gz"
  "shadowsocks@.service"
  "shadowsocks-server@.service")
md5sums=('832181392b6164259134e3e3fe1c72bd'
         'ea0301ecfb76f66b9edafc2a3f2015cf'
         'd26ab75cfad5f9cabfccbcbb9801950a'
         'b69a7bc69bd9138e3d092ced44a102a3')

package() {
  install -D -m755 "shadowsocks-local-linux64-${pkgver}" "$pkgdir/usr/bin/sslocal"
  install -D -m755 "shadowsocks-server-linux64-${pkgver}" "$pkgdir/usr/bin/ssserver"

  install -d "$pkgdir/etc/shadowsocks"
  install -D -m644 shadowsocks@.service "$pkgdir/usr/lib/systemd/system/shadowsocks@.service"
  install -D -m644 shadowsocks-server@.service "$pkgdir/usr/lib/systemd/system/shadowsocks-server@.service"
}

# vim:set ts=2 sw=2 et:
