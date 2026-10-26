# Maintainer: houdert6: houdert6@gmail.com
pkgname=xdg-houd-theme
pkgver=0.1.0
pkgrel=1
pkgdesc='xdg-houd-theme is a WIP xdg desktop portal implementation for the Settings interface that sets permanent dark mode'
arch=('x86_64')
url='https://github.com/houdert6/xdg-houd-theme'
license=('GPL-3.0-or-later')
depends=('xdg-desktop-portal')
makedepends=('git', 'cargo')
provides=('xdg-desktop-portal-impl')
source=('git+https://github.com/houdert6/xdg-houd-theme.git')

build() {
    cd 'xdg-houd-theme'
    cargo build --release
}

package() {
    cd 'xdg-houd-theme'
    install -Dm755 'target/release/xdg-houd-theme' '$pkgdir/usr/lib/xdg-houd-theme'
    install -Dm644 'configs/houdtheme.portal' '$pkgdir/usr/share/xdg-desktop-portal/portals/houdtheme.portal'
    install -Dm644 'configs/xdg-desktop-portal-houdtheme.service' '$pkgdir/usr/lib/systemd/user/xdg-desktop-portal-houdtheme.service'
    install -Dm644 'configs/org.freedesktop.impl.portal.desktop.houdtheme.service' '$pkgdir/usr/share/dbus-1/services/org.freedesktop.impl.portal.desktop.houdtheme.service'
}
