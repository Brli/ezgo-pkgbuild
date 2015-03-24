# Initialized

pkgbase=ezgo
pkgname=('grub2-themes-ezgo' 'ezgo-wallpapers' 'ezgo-chem' 'ezgo-doc' 'ezgo-gsyan' 'ezgo-kde' 'ezgo-menu' 'ezgo-misc'
         'ezgo-npa' 'ezgo-phet' 'ezgo-usgs' 'ezgo-wordtest' 'ezgo-tasks')
pkgver=12.0
pkgrel=1
makedepends=()
arch=('x86_64')
source=("git://anonscm.debian.org/blends/projects/ezgo.git"
	'50_ezgo.cfg'
	# ezgo-chem elements
	"ftp://goodhorse.idv.tw/debian-ezgo/ezgo-chem/chemstru_ezgo12.tar.gz"
	'chemical_struct.desktop'
	''
	'')
sha1sums=('SKIP'
	  'be1ed0b3f1da77ce9393eea84413193e771ebac2'
	  # ezgo-chem elements
	  'bf477a9e0ed96b16ecb1c99b6ee5272916ed9ec7'
	  'c8c01ff2c8dcb8207fb58543e4711fa935389fb6'
	  ''
	  '')

# FIXME: seperated into ezgo-wallpaper, kde-plasma-themes-ezgo, 
#        kde-ksplash-themes-ezgo, and grub2-themes-ezgo
  
package_ezgo-wallpapers() {
  pkgdesc='Set of wallpapers sepecified for Ezgo project'
  install=${pkgname}.install
  # KDE wallpaper
  # Install images
  cd ${srcdir}/${pkgbase}/${pkgname}/wallpaper
  for px in 1366x768 1920x1080 2560x1600; do
    install -Dm644 ezgo12-wallpaper-${px}.png ${pkgdir}/usr/share/wallpapers/ezgo/contents/images/${px}.png
  done
  # Install metadata
  install -Dm644 ezgo-wallpaper.png.desktop ${pkgdir}/usr/share/wallpapers/ezgo/metadata.desktop
}

package_grub2-themes-ezgo() {
  group=('ezgo-artwork')
  depends=('grub')
  # GRUB2 background
  cd ${srcdir}/${pkgbase}/${pkgname}/grub/
  install -Dm644 ${srcdir}/50_ezgo.cfg ${pkgdir}/etc/grub.d/50_ezgo.cfg
  install -Dm644 ezgo-splash-grub-640.png ${pkgdir}/usr/share/grub/themes/ezgo/ezgo-splash-grub-640.png
  install -Dm644 ezgo-splash-grub.png ${pkgdir}/usr/share/grub/themes/ezgo/ezgo-splash-grub.png
}
  # FIXME: KDM themes
  # TODO: SDDM themes
  # FIXME: Ksplash themes

package_ezgo-chem() {
  install -Dm644 ${srcdir}/chemical_struct.desktop ${pkgdir}/usr/share/applications/chemical_struct.desktop
  install -dm755 ${pkgdir}/usr/share/ezgo/ezgo-prt/chemical_structures
  cp -rv ${srcdir}/chemical_structures_ezgo12/* ${pkgdir}/usr/share/ezgo/ezgo-prt/chemical_structures/
}

package_ezgo-doc() {
}