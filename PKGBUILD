# Maintainer: Jonas Heinrich <onny@project-insanity.org>
# Contributor: Jonas Heinrich <onny@project-insanity.org>

# Upstream name of extension:
_extname=MultimediaViewer
# Variant valid as package name:
_extpkgname=multimediaviewer

pkgname=mediawiki-$_extpkgname-git
pkgver=r1305.ed5d49f
pkgrel=1
pkgdesc="Provides a better experience to users when they click on thumbnails in a page"
source=("git+https://gerrit.wikimedia.org/r/mediawiki/extensions/$_extname")
md5sums=("SKIP")
arch=("any")
url="http://www.mediawiki.org/wiki/Extension:$_extname"
license=("GPL")
depends=("mediawiki")
makedepends=("git")
provides=("mediawiki-$_extpkgname")
conflicts=()

pkgver() {
  cd $_extname
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  # Target extension directory of MediaWiki:
  _extdir="$pkgdir/usr/share/webapps/mediawiki/extensions"
  mkdir -p "$_extdir"
  rsync -a $_extname "$_extdir/" --exclude .git
}
