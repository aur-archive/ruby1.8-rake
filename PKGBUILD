# Maintainer: Hilton Medeiros <medeiros.hilton at gmail dot com>
# Contributor: Jacek Roszkowski <j.roszk@gmail.com>

pkgname=ruby1.8-rake
pkgver=0.8.7
_realname="rake"
pkgrel=3
pkgdesc="A simple ruby build program with capabilities similar to make"
arch=(any)
url="http://rake.rubyforge.org"
license=("MIT")
depends=('ruby1.8')
makedepends=('rubygems1.8')
source=(http://gems.rubyforge.org/gems/$_realname-$pkgver.gem)
noextract=($_realname-$pkgver.gem)
md5sums=('d9eb83525310ad1a0e8a3eeddfe3c65f')

build() {
  cd $srcdir
}

package() {
  cd $srcdir
  local _gemdir="$(ruby-1.8 -rubygems -e'puts Gem.default_dir')"
  gem-1.8 install --ignore-dependencies -i "$pkgdir$_gemdir" ${_realname}-$pkgver.gem
  install -d $pkgdir/usr/bin
  ln -s $_gemdir/bin/rake $pkgdir/usr/bin/rake-1.8
}
