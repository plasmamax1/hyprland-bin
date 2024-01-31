# Maintainer: Amit Prayaga <amit.prayaga@protonmail.com>

pkgname=hyprland-bin
pkgver=v0.20.1beta
pkgrel=1
pkgdesc="Hyprland is a dynamic tiling Wayland compositor based on wlroots that doesnt sacrifice on its looks."
arch=('x86_64')
url=https://github.com/hyprwm/Hyprland
license=('BSD')
depends=('libxkbcommon' 'libxcomposite' 'libxrender' 'pango' 'seatd' 'xcb-util' 'xcb-util-keysyms' 'xcb-util-wm' 'xorg-xinput')
optdepends=('xorg-xwayland: run X clients under wayland')
makedepends=('git' 'gdb' 'meson' 'wayland-protocols')
source=("git+$url#tag=$pkgver")
md5sums=('SKIP')

build() {
  cd $pkgname

  # wlroots statically linked
  arch-meson _build
  ninja -C _build
}

package() {
  cd $pkgname
  DESTDIR="$pkgdir" ninja -C _build install
  rm -r $pkgdir/usr/{include,lib}
}