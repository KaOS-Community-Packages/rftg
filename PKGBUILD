pkgname=rftg
pkgver=0.9.4
pkgrel=1
pkgdesc='Singleplayer and online implementation of the card game Race for the Galaxy by Tom Lehman.'
arch=('x86_64')
url='http://keldon.net/rftg/'
license=('GPL')
source=("http://keldon.net/rftg/$pkgname-$pkgver.tar.bz2"
        "$pkgname.desktop"
        'rftg.svg')
sha512sums=('76275851cd4f6200042ee66c323fb8251f37ff7f7804940414d406e26428bc551e93bd0c79760df5b36fc1c95d8d3e7d5cab9f81fcf15f6ec48812ecdea000be' '09dac585610efa141517aa9aebac9aa683057be10de18dc35de91e44b0d476dd86c3a4395f2a375f1d8ac4c50d5a29ec42d416069119f5aef2d919f04c14a3a8' 'e84ba4f069c27a48361fa224e65a9391ddbe0409c1f02d43964b3a34ffcd278f12792d0fee7f4bbb282a6bdd193767d32d73b43642d35e7c6555d46db36877d0')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  ./configure --prefix=/usr
  make
}


package() {
  cd "$srcdir/$pkgname-$pkgver"
 
  make DESTDIR="$pkgdir/" install
  install -D -m644 "$srcdir/$pkgname.desktop" "$pkgdir/usr/share/applications/$pkgname.desktop"
  install -D -m644 "$srcdir/$pkgname.svg" "$pkgdir/usr/share/rftg/$pkgname.svg"
}

