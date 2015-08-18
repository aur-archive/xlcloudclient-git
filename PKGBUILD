# Maintainer: Felix Yan <felixonmars@gmail.com>

pkgname=xlcloudclient-git
_gitname=XLCloudClient
pkgver=0.98
pkgrel=1
pkgdesc="GUI client of Xunlei (Thunder) cloud"
arch=('i686' 'x86_64')
url="https://github.com/CaledoniaProject/XLCloudClient"
license=('GPL2')
depends=('qt4' 'qtwebkit' 'qjson' 'phonon')
makedepends=('git')
source=("git://github.com/CaledoniaProject/$_gitname.git"
        "CloudClient.desktop")
install=xlcloudclient.install

pkgver() {
  cd "$srcdir/$_gitname"
  echo "0.$(git rev-list --count HEAD)"
}

build() {
  cd "$srcdir/$_gitname"

  qmake-qt4 PREFIX=/usr
  make
}

package() {
  cd "$srcdir/$_gitname"
  #make INSTALL_ROOT="$pkgdir" install
  install -Dm755 CloudClient "$pkgdir/usr/bin/CloudClient"
  install -Dm644 "$srcdir/CloudClient.desktop" "$pkgdir/usr/share/applications/CloudClient.desktop"
  install -Dm644 resources/images/thunder-256.png "$pkgdir/usr/share/icons/hicolor/256x256/apps/thunder-256.png"
}

md5sums=('SKIP'
         '9bbcebc56bfda2d668f69484a92269f9')
