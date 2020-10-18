# Contributor: speps <speps at aut dot archlinux dot org>
# Contributor: Reihar <reihar at necronomicon dot fr> 

pkgname=plowshare-git
pkgver=2.1.7.r2.g29911a50
pkgrel=2
pkgdesc="Command-line downloader and uploader for Rapidshare, Mediafire and other file sharing websites."
arch=('any')
url="https://github.com/mcrapet/plowshare"
license=('GPL3')
depends=('curl' 'recode' 'js52')
makedepends=('git')
optdepends=('bash-completion: enable bash auto completion'
            'libcaca: ascii display for no X server'
            'tiv: ascii display for no X server'
            'aview: ascii display for no X server')
provides=('plowshare')
conflicts=('plowshare')
replaces=('plowshare-svn')
source=("$pkgname::git+https://github.com/mcrapet/plowshare.git" "js52.patch")
sha256sums=('SKIP'
            'd00a391d18949e5b4032238f39ec3710803fed027cfa30b49f87cd1b0d246037')

pkgver() {
  cd "$pkgname"
  git describe --long --tags | sed 's/.//;s/-/.r/;s/-/./'
}

prepare() {
  cd "$pkgname"
  patch --forward --strip=1 --input="${srcdir}/js52.patch"
}

package() {
  cd "$pkgname"
  DESTDIR="$pkgdir/" PREFIX=/usr make
}

# vim:set ts=2 sw=2 et:
