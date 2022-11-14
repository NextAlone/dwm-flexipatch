# Maintainer: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Contributor: Dag Odenhall <dag.odenhall@gmail.com>
# Contributor: Grigorios Bouzakis <grbzks@gmail.com>

pkgname=dwm
pkgver=6.3
pkgrel=1
pkgdesc="A dynamic window manager for X"
url="https://dwm.suckless.org"
arch=('x86_64')
license=('MIT')
options=(zipman)
depends=('libx11' 'libxinerama' 'libxft' 'freetype2')
source=(dwm.c
        drw.c
        drw.h
        util.c
        util.h
        Makefile
        config.mk
        config.h
        config.def.h
        patches.h
        patches.def.h
        transient.c
        onedark.h
        dwm.1
        LICENSE
        README
        dwm.desktop
        patch.zip
)

sha256sums=('SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP')

build() {
  cd "$srcdir"
  make
}

package() {
  cd "$srcdir"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -Dm644 README "$pkgdir/usr/share/doc/$pkgname/README"
  install -Dm644 dwm.desktop "$pkgdir/usr/share/xsessions/dwm.desktop"
}
