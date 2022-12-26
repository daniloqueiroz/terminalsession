# Maintainer: Danilo Queiroz <dpenna.queiroz@gmail.com>
pkgname=terminalsession
pkgver=1.0
pkgrel=1
pkgdesc="A very simple terminal session manager built on top of dtach and fzf."
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
  git describe --long --tags | sed 's/-/.r/;s/-/./'
}
