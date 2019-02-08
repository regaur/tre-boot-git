# Maintainer: Jan Boelsche <jan@lagomorph.de>

pkgname=tre-boot-git
pkgver=1.4.0.r18.01f4aaa
pkgrel=1
pkgdesc="Serve webapps via ssb-ws http server"
arch=('any')
url=""
license=('GPL')
groups=()
depends=('scuttlebot')
depends=('ssb-revisions')
makedepends=('git' 'npm')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
replaces=()
backup=()
options=()

source=("git+ssh://git@github.com/regular/${pkgname%-git}.git")

sha256sums=('SKIP')

pkgver() {
	cd "$srcdir/${pkgname%-git}"
  printf "%s.r%s.%s" "$(node -e 'console.log(require("./package.json").version)')" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package () {
	cd "$srcdir/${pkgname%-git}"
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" regular/${pkgname%-git}
}
