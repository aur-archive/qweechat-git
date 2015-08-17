# Maintainer: Logan Gorence <loganjohngorence@gmail.com>
# Contributor: qozy <qozy@qozy.eu>
pkgname=qweechat-git
pkgver=9036a59
pkgrel=1
pkgdesc="Qt GUI for WeeChat relay"
arch=('any')
url="http://git.savannah.gnu.org/gitweb/?p=qweechat.git;a=summary"
license=('GPL')
depends=('python2' 'python2-pyqt' 'python2-sip')
makedepends=('git')
source=('git://github.com/weechat/qweechat.git' 'qweechat.desktop' 'qweechat.run')
md5sums=('SKIP'
         'b0fefa6571595811a9e569c6c7ce7b40'
         'b831d39c484aad07ad338ab67be5ff74')

_gitname=qweechat

build() {
  cd $_gitname
  python2 setup.py build
}

package() {
  cd $_gitname
  python2 setup.py install --root $pkgdir -O2
  install -m 644 -D $srcdir/qweechat.desktop $pkgdir/usr/share/applications/qweechat.desktop
  install -m 755 -D $srcdir/qweechat.run $pkgdir/usr/bin/qweechat
  install -m 644 -D $srcdir/$_gitname/$_gitname/data/icons/weechat_icon_32.png $pkgdir/usr/share/icons/hicolor/32x32/apps/qweechat.png
}

pkgver() {
  cd $_gitname
  git describe --always | sed 's|-|.|g'
}
# vim:set ts=2 sw=2 et:
