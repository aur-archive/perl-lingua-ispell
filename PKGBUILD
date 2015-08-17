# Mainainer: uberushaximus <uberushaximus AT gmail DOT com>
# Generator  : CPANPLUS::Dist::Arch 1.29

pkgname='perl-lingua-ispell'
pkgver='0.07'
pkgrel='3'
pkgdesc="Encapsulates access to the Ispell program"
arch=('any')
license=('PerlArtistic' 'GPL')
options=('!emptydirs')
depends=('perl' 'ispell')
url='https://metacpan.org/pod/Lingua::Ispell'
source=("http://cpan.metacpan.org/authors/id/J/JD/JDPORTER/Lingua-Ispell-0.07.tar.gz")
sha512sums=('2c7b71115c5db5d3aa91126a36e80b94dac8771e81638fd9de8a561cebca64262e6596aed2ebee3ba131590f23ac8ddef3157db929c44d6333157ac209a9facc')
_distdir="Lingua-Ispell-0.07"

build() {
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""                 \
      PERL_AUTOINSTALL=--skipdeps                            \
      PERL_MM_OPT="INSTALLDIRS=vendor DESTDIR='$pkgdir'"     \
      PERL_MB_OPT="--installdirs vendor --destdir '$pkgdir'" \
      MODULEBUILDRC=/dev/null

    cd "$srcdir/$_distdir"
    sed 's|/usr/local/bin/ispell|/usr/bin/ispell|g' -i lib/Lingua/Ispell.pm
    /usr/bin/perl Makefile.PL
    make
  )
}

check() {
  cd "$srcdir/$_distdir"
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""
    make test
  )
}

package() {
  cd "$srcdir/$_distdir"
  make install
  find "$pkgdir" -name .packlist -o -name perllocal.pod -delete
}
