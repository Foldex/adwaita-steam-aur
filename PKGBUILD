# Maintainer: Mattia Borda <mattiagiovanni.borda@icloud.com>

pkgname=adwaita-for-steam
pkgver=1.2
pkgrel=1
pkgdesc='A skin installer to make Steam look more like a native GNOME app'
arch=(any)
url=https://github.com/tkashkin/$pkgname
license=(MIT)
depends=(cantarell-fonts)
optdepends=("steam: if you don't use the flatpak version of Steam")
makedepends=(git)
source=("git+$url#tag=v$pkgver"
        "adwaita-for-steam.sh")
b2sums=('SKIP'
        '047789df2dbcd1903bd35b7a8b120d9f6449424ddb0602bad1a060c1cb541835075d2e698b42eb637bda7b1d102f5e395653118bd65df7475322b4e4d3c86608')

package() {
  install "adwaita-for-steam.sh" -Dm755 "$pkgdir/usr/bin/adwaita-for-steam"

  cd $pkgname

  find colorthemes -type f -exec install -Dm644 "{}" "$pkgdir/usr/share/$pkgname/{}" \;
  find fonts -type f -exec install -Dm644 "{}" "$pkgdir/usr/share/$pkgname/{}" \;
  find web -type f -exec install -Dm644 "{}" "$pkgdir/usr/share/$pkgname/{}" \;
  install -Dm644 "install.py" "$pkgdir/usr/share/$pkgname/"
  install -Dm644 LICENSE -t "$pkgdir"/usr/share/licenses/$pkgname
}
