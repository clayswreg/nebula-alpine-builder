# Maintainer: Automation <automation@localhost.local>
# Maintainer: Your Name <you@example.com>
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
