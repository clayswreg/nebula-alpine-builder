# Maintainer: Automation
pkgname=nebula-custom
pkgver=1.10.0
pkgrel=0
pkgdesc="Nebula for Raspberry Pi 3"
arch="aarch64"
url="https://github.com/slackhq/nebula"
license="MIT"
source="https://github.com/slackhq/nebula/releases/download/v$pkgver/nebula-linux-arm64.tar.gz
        nebula.initd"
options="!strip !check"

package() {
    mkdir -p "$pkgdir"/etc/nebula
    install -Dm755 "$srcdir"/nebula "$pkgdir"/usr/local/bin/nebula
    install -Dm755 "$srcdir"/nebula-cert "$pkgdir"/usr/local/bin/nebula-cert
    install -Dm755 "$srcdir"/nebula.initd "$pkgdir"/etc/init.d/nebula
}
