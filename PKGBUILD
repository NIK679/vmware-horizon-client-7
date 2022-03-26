 
# Maintainer: Nikhil Alex <nikhil.wtp@gmail.com>

pkgname='vmware-horizon-client-7'
pkgver=5.5.4
build=19467421
_cart='CART23FQ1_LIN_554_TARBALL'
pkgrel=1
pkgdesc='VMware Horizon Client connect to VMware Horizon virtual desktop'
arch=('x86_64')
url='https://www.vmware.com/go/viewclients'
license=('custom')
source=("https://download3.vmware.com/software/${_cart}/VMware-Horizon-Client-Linux-${pkgver}-${build}.tar.gz")
sha256sums=(c55b7cb5d0923344aee9d77b7b9423f1958f8b011c084e1b036e9283a0b548ca)

prepare() {
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${build}/x64/"
    tar xzvf VMware-Horizon-Client-${pkgver}-${build}.x86_64.tar.gz
    tar xzvf VMware-Horizon-PCoIP-${pkgver}-${build}.x64.tar.gz
}

package() {
    mkdir -p "${pkgdir}/usr/share/"
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${build}/x64/VMware-Horizon-Client-${pkgver}-${build}.x86_64"
    sed -i 's/vmware-view %u/XDG_CURRENT_DESKTOP=GNOME GTK_THEME=Default vmware-view %u/' share/applications/vmware-view.desktop
    cp -a bin "${pkgdir}/usr/"
    cp -a lib "${pkgdir}/usr/"
    cp -a doc "${pkgdir}/usr/share/"
    cp -a share/locale "$pkgdir/usr/share/"
    cp -a share/applications "$pkgdir/usr/share/"
    cp -a share/icons "$pkgdir/usr/share/"
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${build}/x64/VMware-Horizon-PCoIP-${pkgver}-${build}.x64"
    cp -a lib "${pkgdir}/usr/"
}
