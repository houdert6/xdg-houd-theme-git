#     PKGBUILD to install xdg-houd-theme
#     Copyright (C) 2026  houdert6
# 
#     This program is free software: you can redistribute it and/or modify
#     it under the terms of the GNU General Public License as published by
#     the Free Software Foundation, either version 3 of the License, or
#     (at your option) any later version.
# 
#     This program is distributed in the hope that it will be useful,
#     but WITHOUT ANY WARRANTY; without even the implied warranty of
#     MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#     GNU General Public License for more details.
# 
#     You should have received a copy of the GNU General Public License
#     along with this program.  If not, see <https://www.gnu.org/licenses/>.


# Maintainer: houdert6: houdert6@gmail.com
pkgname=xdg-houd-theme
pkgver=0.1.0
pkgrel=1
pkgdesc='xdg-houd-theme is a WIP xdg desktop portal implementation for the Settings interface that sets permanent dark mode'
arch=('x86_64')
url='https://github.com/houdert6/xdg-houd-theme'
license=('GPL-3.0-or-later')
depends=('xdg-desktop-portal')
makedepends=('git' 'cargo')
provides=('xdg-desktop-portal-impl')
source=('git+https://github.com/houdert6/xdg-houd-theme.git')
sha256sums=('SKIP')

build() {
    cd 'xdg-houd-theme'
    cargo build --release
}

package() {
    cd 'xdg-houd-theme'
    install -Dm755 'target/release/xdg-houd-theme' "$pkgdir/usr/lib/xdg-houd-theme"
    install -Dm644 'configs/houdtheme.portal' "$pkgdir/usr/share/xdg-desktop-portal/portals/houdtheme.portal"
    install -Dm644 'configs/xdg-desktop-portal-houdtheme.service' "$pkgdir/usr/lib/systemd/user/xdg-desktop-portal-houdtheme.service"
    install -Dm644 'configs/org.freedesktop.impl.portal.desktop.houdtheme.service' "$pkgdir/usr/share/dbus-1/services/org.freedesktop.impl.portal.desktop.houdtheme.service"
}
