# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=kiosk-initcpio
pkgver=1.19
pkgrel=1
pkgdesc="Create initramfs for compressed, optionally encrypted, read-only root filesystem"
arch=('x86_64')
license=('GPL')
depends=('linux')
optdepends=('plymouth')

source=(
  'kiosk.preset'
  'mkinitcpio-kiosk-plymouth.conf'
  'mkinitcpio-kiosk.conf'
  'archiso_shutdown'
  'hooks-archiso_shutdown'
  'hooks-archiso_loop_mnt'
  'hooks-archiso'
  'install-archiso_shutdown'
  'install-archiso_kms'
  'install-archiso_loop_mnt'
  'install-archiso'
)

sha256sums=('131464045be52c09565ffbb182dc2de5ee5c38779df9d4016149fd70ab0947e9'
            '4518ac38e96943bb2f92066180a12be8c72ca3126bebb0cf4fc0e50858e7b605'
            'd3f85a578f049fb325f274fb0d78c0c99919aa6299d236e4ddb1f27cdf19a4ac'
            '8d96005607c34af4792f79bfffb021c4d89077945b3004f19f56647141ff8166'
            'b40771a171b0b182b98670885340bdc12ca86f6eb2de8c565316091baf7ff3c8'
            '7fa7d65b0228b5caa5344964739347a999afbfa63bf86e67193668f9337936db'
            'f58392aba5b43010f066d215b88cf2d2b42613be676b221a67d859644bf29d16'
            '04c58d29c882398a596d5e934016657853c526247f51655fb400f917197aebd6'
            'd383ba54094826fbd7c9da37eefdabf0be770bf6bc9a998427162884dc8d0c94'
            '8edde9dffa07ead6bfc6277f145385b6152215144d5355c6e21911c32d0a869c'
            '2d3244f7f3fade4b95302fece24775ecc1684082b1fa2149f3fadaec8ebcd943')

package() {
  mkdir -p ${pkgdir}/etc/initcpio/{hooks,install}
  for p in hooks install; do
    for f in $(ls|grep "^$p-"); do
      cp $f ${pkgdir}/etc/initcpio/$p/${f##$p-}
    done
  done

  install -Dt ${pkgdir}/etc/mkinitcpio.d/ kiosk.preset
  install -Dt ${pkgdir}/etc/ mkinitcpio-kiosk-plymouth.conf
  install -Dt ${pkgdir}/etc/ mkinitcpio-kiosk.conf
  install -Dt ${pkgdir}/etc/initcpio/ archiso_shutdown
}

