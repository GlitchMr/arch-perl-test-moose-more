# Maintainer: Konrad Borowski <glitchmr@myopera.com>
pkgname=perl-test-moose-more
pkgver=0.018
pkgrel=1
pkgdesc='More tools for testing Moose packages'
arch=('any')
url='https://metacpan.org/module/Test::Moose::More'
license=('LGPL2')
depends=('perl-data-optlist'
'perl-moose-autobox'
'perl-moose'
'perl6-junction'
'perl-sub-exporter')
makedepends=('perl-file-temp'
'perl-tap-simpleoutput'
'perl-namespace-autoclean')
provides=()
conflicts=()
replaces=()
backup=()
options=('!emptydirs')
install=
source=("http://search.cpan.org/CPAN/authors/id/R/RS/RSRCHBOY/Test-Moose-More-$pkgver.tar.gz")
md5sums=('596f3b0cc7ad246f073cc4530cd00bf6')

build() {
  cd "$srcdir/Test-Moose-More-$pkgver"

  # Setting these env variables overwrites any command-line-options we don't want...
  export PERL_MM_USE_DEFAULT=1 PERL_AUTOINSTALL=--skipdeps \
    PERL_MM_OPT="INSTALLDIRS=vendor DESTDIR='$pkgdir'" \
    PERL_MB_OPT="--installdirs vendor --destdir '$pkgdir'" \
    MODULEBUILDRC=/dev/null

  { /usr/bin/perl Makefile.PL &&
    make &&
    make test &&
    make install; } || return 1
}
