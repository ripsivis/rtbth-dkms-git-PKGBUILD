# Maintainer: Onur Ankut <ripsivis@gmail.com>
# Contributor: Felix Golatofski <contact@xdfr.de>
# Contributor: Jesse Watson <me@9mmtylenol.me>
# Contributor: Alex Amadori <tacchinotacchi@gmail.com>
# Contributor: SirToffski <https://github.com/SirToffski>

_name=rtbth-dkms
pkgname=rtbth-dkms-git
pkgver=3.9.6.r16.g1eb32cf
pkgrel=1
pkgdesc="Kernel module sources for Ralink RT3290 Bluetooth."
arch=('i686' 'x86_64')
url='http://www.mediatek.com/'
license=('mixed')
depends=('dkms')
optdepends=('bluez: Canonical implementation of Bluetooth protocol'
            'bluez-utils: Utilities for Bluez')
conflicts=('rtbth-dkms')
provides=('rtbth')
install='rtbth-dkms.install'
source=('git+https://github.com/ripsivis/rtbth-dkms.git')
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/$_name"
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
  cd "$srcdir/"
  install -d -m 755 "${pkgdir}"/usr/bin
  install -d -m 755 "${pkgdir}"/usr/src
  install -D -m 644 "${_name}/tools/rtbth.service" "${pkgdir}"/usr/lib/systemd/system/rtbth.service
  install -D -m 755 "${_name}/tools/rtbth" "${pkgdir}"/usr/bin/rtbth
  install -D -m 755 "${_name}/tools/rtbt" "${pkgdir}/usr/bin/rtbt"
  cp -r "${_name}"/ "${pkgdir}/usr/src/rtbth-${pkgver}"
}
