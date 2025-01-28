# Maintainer: J0pp3rt <some@email.net>
pkgname=python-tikzplotlib-git-fork
pkgver=r1631.31fdf75
pkgrel=1
pkgdesc="Convert matplotlib figures into TikZ/PGFPlots"
url="https://github.com/J0pp3rt/tikzplotlib"
makedepends=(git python-flit-core python-build python-installer python-wheel)
depends=(python python-matplotlib python-numpy python-pillow python-webcolors)
provides=("python-tikzplotlib=$pkgver")
conflicts=(python-matplotlib2tikz python-tikzplotlib python-tikzplotlib-git)
replaces=(python-matplotlib2tikz)
license=(MIT)
arch=(any)
source=("git+$url.git")
sha256sums=('SKIP')

pkgver() {
        cd "$srcdir/tikzplotlib"
        printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"  
}

build() {
        cd "$srcdir/tikzplotlib"
        python -m build --wheel --no-isolation
}

package() {
        cd "$srcdir/tikzplotlib"
        python -m installer --destdir="$pkgdir" dist/*.whl
        install -Dm644 "LICENSE" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
