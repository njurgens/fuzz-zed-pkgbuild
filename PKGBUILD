_realname=fuzz
pkgname=fuzz-zed
pkgver=3.4.1
pkgrel=1
pkgdesc="The fuzz type-checker for Z"
arch=('i686' 'x86_64')
url="http://spivey.oriel.ox.ac.uk/mike/fuzz/"
license=('MIT')
groups=()
depends=()
makedepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
source=("http://spivey.oriel.ox.ac.uk/mike/fuzz/$_realname-$pkgver.tgz")
noextract=()
md5sums=('abb703a693e024aa2aa8b27abafeeded')

_fix_makefiles() {
    sed -i -e 's|^BINDIR =.*|BINDIR = $(DESTDIR)/usr/local/bin|g' Makefile
    sed -i -e 's|^LIBDIR =.*|LIBDIR = $(DESTDIR)/usr/local/lib|g' Makefile
    sed -i -e 's|^TEXDIR =.*|TEXDIR = $(DESTDIR)/usr/lib/tex/texmf/tex|g' Makefile
    sed -i -e 's|^MFDIR =.*|MFDIR = $(DESTDIR)/usr/lib/tex/texmf/fonts/source/local|g' Makefile
    #sed -i -e 's|^\t$(INSTALL)|\t$(INSTALL) -D|g' Makefile
    sed -i -e 's|^CPP=.*|CPP=cpp|g' src/Makefile
}

_mkdirs() {
    mkdir -p $pkgdir/usr/local/bin
    mkdir -p $pkgdir/usr/local/lib
    mkdir -p $pkgdir/usr/lib/tex/texmf/tex
    mkdir -p $pkgdir/usr/lib/tex/texmf/fonts/source/local
}

build() {
    cd $srcdir/$_realname-$pkgver
    _fix_makefiles
    make CFLAGS=""
}

package() {
    cd $srcdir/$_realname-$pkgver
    _mkdirs
    make DESTDIR=$pkgdir install
}
# vim:syntax=sh
