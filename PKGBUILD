 
# Maintainer: Nikhil Alex <nikhil.wtp@gmail.com>

pkgname='vmware-horizon-client-7'
pkgver=5.5.2
build=18035020
_cart='CART21FQ3'
pkgrel=1
pkgdesc='VMware Horizon Client connect to VMware Horizon virtual desktop'
arch=('x86_64')
url='https://www.vmware.com/go/viewclients'
license=('custom')
source=("https://download3.vmware.com/software/view/viewclients/${_cart}/VMware-Horizon-Client-linux-${pkgver}-${build}.tar.gz")
sha256sums=(cbfa8f307f5d0ea9f50a710b998debec89e3a4f6c68249dc20ef2638d93302a7)

prepare() {
    cd "${srcdir}/vmware-view-client-linux-${pkgver}-${build}/x64/"
    tar xzvf VMware-Horizon-Client-${pkgver}-${build}.x86_64.tar.gz
    tar xzvf VMware-Horizon-PCoIP-${pkgver}-${build}.x64.tar.gz
}

package() {
    mkdir -p "${pkgdir}/usr/share/"
    cd "${srcdir}/vmware-view-client-linux-${pkgver}-${build}/x64/VMware-Horizon-Client-${pkgver}-${build}.x86_64"
    sed -i 's/vmware-view %u/XDG_CURRENT_DESKTOP=GNOME GTK_THEME=Default vmware-view %u/' share/applications/vmware-view.desktop
    cp -a bin "${pkgdir}/usr/"
    cp -a lib "${pkgdir}/usr/"
    cp -a doc "${pkgdir}/usr/share/"
    cp -a share/locale "$pkgdir/usr/share/"
    cp -a share/applications "$pkgdir/usr/share/"
    cp -a share/icons "$pkgdir/usr/share/"
    cd "${srcdir}/vmware-view-client-linux-${pkgver}-${build}/x64/VMware-Horizon-PCoIP-${pkgver}-${build}.x64"
    cp -a lib "${pkgdir}/usr/"
}
