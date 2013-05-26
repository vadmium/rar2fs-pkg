pkgname=rar2fs
pkgver=1.17.0
_rls="$pkgname-$pkgver"
pkgrel=1
pkgdesc="Fuse file system for reading Rar archives"
arch=(i686 x86_64)
license=(GPL3)
url="https://code.google.com/p/$pkgname"
depends=(fuse "libunrar<1:5")
makedepends=("libunrar<1:5")

source=("https://$pkgname.googlecode.com/files/$_rls.tar.gz")
sha1sums=(fe08cfdd77d27f124d1092ee83cfb3297b712323)

source+=(http://www.rarlab.com/rar/unrarsrc-4.2.4.tar.gz)
sha1sums+=(1cc29603fb4e4df16a3aa9bfc7da1afaf0923259)

build() {
    cd "$srcdir/$_rls"
    ./configure --prefix=/usr --with-unrar=../unrar
    make
}

package() {
    make -C "$srcdir/$_rls" install DESTDIR="$pkgdir"
}
