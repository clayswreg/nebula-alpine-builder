# Maintainer: Automation <automation@localhost.local>
pkgname=nebula-custom
pkgver=1.10.0
pkgrel=0
pkgdesc="Nebula for Raspberry Pi"
arch="aarch64 armv7"
url="https://github.com/slackhq/nebula"
license="MIT"

case "$CARCH" in
    aarch64) _arch="arm64" ;;
    armv7)   _arch="arm-7" ;;
esac

source="nebula-${pkgver}.tar.gz::https://github.com/slackhq/nebula/releases/download/v${pkgver}/nebula-linux-${_arch}.tar.gz
        nebula.initd"
options="!strip !check"
# This tells Alpine to bundle the init script correctly
subpackages="$pkgname-openrc:openrc_script:noarch"

package() {
    mkdir -p "$pkgdir"/usr/bin
    install -Dm755 "$srcdir"/nebula "$pkgdir"/usr/bin/nebula
    install -Dm755 "$srcdir"/nebula-cert "$pkgdir"/usr/bin/nebula-cert
    
    mkdir -p "$pkgdir"/etc/nebula
}

openrc_script() {
    install -Dm755 "$srcdir"/nebula.initd "$subpkgdir"/etc/init.d/nebula
}
