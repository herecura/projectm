# Maintainer: Giancarlo Razzolini <grazzolini@archlinux.org>
# Contributor: Alexander F Rødseth <xyproto@archlinux.org>
# Contributor: Lukas Fleischer <lfleischer@archlinux.org>
# Contributor: Alexander Baldeck <alexander@archlinux.org>
# Contributor: Denis A. Altoe Falqueto <denisfalqueto@gmail.com>

pkgname=projectm
pkgver=3.1.0
pkgrel=1
pkgdesc='Music visualizer which uses 3D accelerated iterative image based rendering'
arch=('x86_64')
url='https://github.com/projectM-visualizer/projectm'
license=('LGPL')
depends=('mesa-libgl' 'glm' 'qt5-base' 'ftgl' 'glew' 'libvisual' 'sdl2' 'libpulse')
source=("https://github.com/projectM-visualizer/$pkgbase/releases/download/v$pkgver/projectM-$pkgver.tar.gz")
sha256sums=('36f67c362d5fa405d73f938c183d8c4a27d1ee6058a68b66c11ace2e89f97da8')

prepare() {
  cd "projectM-$pkgver"

  #patch -p1 -i ../projectm-test-opengl.patch
  #patch -p1 -i ../projectm-install-vera-ttf.patch
  #sed 's/projectM_isnan/std::isnan/g' -i src/libprojectM/Renderer/BeatDetect.cpp 
  #patch -p1 -i ../projectm-gcc6.patch
}

build() {
  cd "projectM-$pkgver"
  ./configure --prefix=/usr --enable-sdl --enable-threading --enable-qt
  make
}

package() {
  cd "projectM-$pkgver"
  make DESTDIR="$pkgdir" install
}

