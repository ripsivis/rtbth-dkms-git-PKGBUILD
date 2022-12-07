# Maintainer: Onur Ankut <ripsivis@gmail.com>
# Contributor: Felix Golatofski <contact@xdfr.de>
# Contributor: Jesse Watson <me@9mmtylenol.me>
# Contributor: Alex Amadori <tacchinotacchi@gmail.com>
# Contributor: SirToffski <https://github.com/SirToffski>
# Contributor: Furkan Karcıoğlu <krc440002@gmail.com>

_name=rtbth-dkms
pkgname=rtbth-dkms-git
pkgver=3.9.6.r7.gce4e65d
pkgrel=1
pkgdesc="Kernel module sources for Ralink RT3290 Bluetooth."
arch=('i686' 'x86_64')
url='http://www.mediatek.com/'
license=('mixed')
depends=('dkms')
optdepends=('bluez: Canonical implementation of bluetooth protocol'
            'bluez-utils: Utilities for Bluez')
conflicts=('rtbth-dkms')
provides=('rtbth')
install='rtbth-dkms.install'
source=('git+https://github.com/ripsivis/rtbth-dkms.git')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$_name"
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
  cd "$srcdir/"
  install -dm755 "$pkgdir/usr/bin"
  install -dm755 "$pkgdir/usr/src"
  install -dm755 "$_name" "$pkgdir/usr/src/$provides-$pkgver"
  install -Dm755 "$_name/tools/rtbt" "$pkgdir/usr/bin/rtbt"
  install -Dm644 rtbth.service "$pkgdir/usr/lib/systemd/system/rtbth.service"
  install -Dm755 rtbth "$pkgdir/usr/bin/rtbth"
}
