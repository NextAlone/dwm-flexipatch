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

sha256sums=('f6a5bda1630dc0add244898143529dcb0209ed5bb7211ffbc89fb357f641b964'
            'ff2c0ab4a1bd722d962a9cd61f46b91ec56a7016d0be86c8c59cda557600f4c5'
            '8864c876c531e2432d3a03987bb752aba32d19623d8e6c390800887939e842bc'
            '1c093b9969daaf3e1a001b924c6c2da3770993916b444dfe65fe39aa0090aa1a'
            '34a0c1e249878faed59891f1afae940bf8526c19f5e74327e10d469c1a73fdef'
            '04fa8c77f89c7807ff803d52325b076ac45e2562f7ad5649afd0b0117c835538'
            '88e12eea9118b225e119ac9809dfa3e3fad5af1ac98210c66799c4944664d42a'
            '65ecf74a8d1897f829734a2d6ca54a836740d70d4443773c0ec4ea9c05d04cd4'
            '08785a5a6c85130f715798a0b7af66e31bb8c9f3a7b53d22f68209b449863e66'
            'd3dad7c43632c113947de49a5a21263ddba5fbc370327329b67b101bc2a44063'
            'ac3f593482fbc58f708f723a949ea772a1f80889746999e5143747d5a40df04c'
            'cd189ba807613dbe51cf12aa7a145b5f620144ba286f146ef5aafc337506fc0a'
            '2a5c92e337ff7e2260fef729ef1330c92b2f68419e60215dc35eaf84d0c1404b'
            'e97f42257c05b7298a15a57c5a579b534ab37a305fc3bdc6f2c9d04788f3ab51'
            '8bbe268a549563fb2895eefd3c43869ca436eda0ba826474334270ad84a7c98d'
            'f0384e29e3f249fcd52a30c35c722fca50e9fabfdeb7725f4073e05170358d86'
            '28c8d5bcaca83b7e945d6f52e91d3941f6d67e489d8a8484cc20546a8149bbf4'
            '749310699eef80f3550f4f4765c548979275a5b12b8ae8fee44977cf6a616373')

build() {
  cd "$srcdir"
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 FREETYPEINC=/usr/include/freetype2
}

package() {
  cd "$srcdir"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -Dm644 README "$pkgdir/usr/share/doc/$pkgname/README"
  install -Dm644 dwm.desktop "$pkgdir/usr/share/xsessions/dwm.desktop"
}
