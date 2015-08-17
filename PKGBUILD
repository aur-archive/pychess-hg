# Maintainer: hbdee <hbdee.arch@gmail.com>
# Contributor: <i.nnikishi@gmail.com>

pkgname=pychess-hg
pkgver=r3053.3f164ce6ca34
pkgrel=1
pkgdesc="Chess client for the GNOME desktop - latest development version"
arch=('any')
url="http://code.google.com/p/pychess/"
license=('GPL')
makedepends=('mercurial')
depends=('python2-rsvg' 'gnome-icon-theme' 'pygtksourceview2' 'gstreamer0.10-python' 'desktop-file-utils')
optdepends=('gstreamer0.10-base-plugins: sound support')
source=('hg+https://pychess.googlecode.com/hg/')
provides=('pychess')
conflicts=('pychess' 'pychess-beta')
install="pychess-hg.install"
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/hg"
  printf "r%s.%s" "$(hg identify -n)" "$(hg identify -i)"
}

prepare() {
  if [[ -d build ]]
  then
    rm -rf build
  fi
   mkdir build
  cp -ar "$srcdir/hg" "$srcdir/build"
}

package() {
  cd "$srcdir/build/hg"
  python2 setup.py install --prefix=/usr --root=$pkgdir
}

