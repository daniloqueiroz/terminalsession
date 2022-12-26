# Maintainer: Danilo Queiroz <dpenna.queiroz@gmail.com>
pkgname=terminalsession
pkgver=r2.9c56ee3
pkgrel=1
pkgdesc="A very simple terminal session manager built on top of dtach and fzf (for interactive mode)."
arch=('x86_64')
url="https://github.com/daniloqueiroz/terminalsession"
license=('GPL3')
depends=('fzf>=0.34.0' 'dtach>=0.9')
provides=('terminalsession')
conflicts=('terminalsession')
source=("${pkgname}::git+https://github.com/daniloqueiroz/terminalsession.git")
md5sums=('SKIP')

package() {
  cd "${srcdir}/${pkgname}"
  install -Dm755 tsctl "$pkgdir/usr/bin/tsctl"
}

pkgver() {
  cd "${srcdir}/${pkgname}"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}
