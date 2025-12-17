# Maintainer: Davide Depau <davide@depau.eu>
# Contributor: Johnathon Clark <john.clark at cantab dot net>
# Contributor: Jan Alexander Steffens (heftig) <heftig@archlinux.org> 
# Contributor: Tom Gundersen <teg@jklm.no>
# Contributor: Thomas Baechler <thomas@archlinux.org>
# Contributor: xerootg <4009802+xerootg@users.noreply.github.com>

# This is a build of the experimental elanmoc2 driver by Davide Depau

pkgname=libfprint-elanmoc2-slg3-git
_pkgname=libfprint
pkgver=1.94.0+9f169dcc
pkgrel=1
pkgdesc="Library for fingerprint readers with patches for the support of the ELAN used in Surface Laptop Go 1, 2 and 3"
url="https://fprint.freedesktop.org/"
arch=(x86_64)
license=(LGPL)
depends=(libgusb pixman nss systemd libgudev)
makedepends=(git meson gtk-doc gobject-introspection glib2-devel)
checkdepends=(cairo)
conflicts=(libfprint)
provides=(libfprint=1.94.0 libfprint-2.so)
groups=(fprint)
source=("git+https://github.com/xerootg/libfprint.git#branch=elanmoc2")
sha256sums=('SKIP')

pkgver() {
  cd $_pkgname
  echo "1.94.0+$(git rev-parse --short=8 HEAD)"
}

prepare() {
  cd $_pkgname
}

build() {
  arch-meson $_pkgname build
  meson compile -C build
}

package() {
  meson install -C build --destdir "$pkgdir"
}
