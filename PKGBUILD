pkgname=clpeak-git
pkgver=1.0.42.g16bea68
pkgrel=1
pkgdesc="A tool which profiles OpenCL devices to find their peak capacities"

arch=('any')
url="https://github.com/krrishnarraj/clpeak"
license=('Public domain')
conflicts=('clpeak')
provides=('clpeak')
makedepends=('git')
source=('git+https://github.com/krrishnarraj/clpeak.git')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/clpeak"
  git describe --always --tags | sed -e 's|^v||' -e 's|-|.|g'
}

prepare() {
  cd "$srcdir/clpeak"
  mkdir build
  cd build
  cmake ..
}

build() {
  cd "$srcdir/clpeak/build"
  make
}

package() {
  mkdir -p "$pkgdir/usr/bin"
  cp -r "$srcdir/clpeak/build/clpeak" "$pkgdir/usr/bin"
  chmod 755 "$pkgdir/usr/bin/clpeak"
}

