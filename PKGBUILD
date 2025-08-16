# Maintainer: Tom Brown <tom@CarlsonSpeed.com>
pkgname=dsf2flac
pkgver=0.4
pkgrel=1
pkgdesc="A utility to convert DSF (DSD) audio files to FLAC (original by hank, updated by dhalsimax)"
arch=('x86_64')
url="https://github.com/dhalsimax/dsf2flac"
license=('GPL3')
depends=('flac')
makedepends=('git' 'cmake')
source=("$pkgname-$pkgver.tar.gz::https://github.com/your/dsf2flac/archive/v$pkgver.tar.gz")
source=("git+https://github.com/dhalsimax/dsf2flac.git")
sha256sums=('SKIP')  # Replace with the actual checksum (run `updpkgsums` later)

build() {
  cd "$srcdir/$pkgname/build"
  sed -i 's/cmake_minimum_required(VERSION 2.6)/cmake_minimum_required(VERSION 3.5)/' ../CMakeLists.txt

  cmake .. -Wno-dev

  cmake --build . --parallel

  make
}

package() {
  cd "$pkgname"

  install -Dm755 build/dsf2flac -t "$pkgdir/usr/bin/"
  install -Dm644 README.md -t "$pkgdir/usr/share/doc/$pkgname/"
}
