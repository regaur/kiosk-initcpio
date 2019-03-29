# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=kiosk-initcpio
pkgver=1.6
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
            'c48843008276fa620238d2562faeb3304cc4c41d1564800c77e8219164e758d0'
            '97276b0f511b782c0b7a61e2a626032b5d63ae4fd996d2a6ba901d0fadaf72f8'
            '7169d7d38b803bd0f95b437c92aacd1f22a6bd6e8a7ebb5a017e04b25f4fb5bf'
            'b40771a171b0b182b98670885340bdc12ca86f6eb2de8c565316091baf7ff3c8'
            'e1c371a465c3f8611f43037a973b826466851d156fdac73e44f9368d053454c6'
            'd1bb9039b27bb40644e78853e0ef68c98c53799cf20d69c121208b4c7060f4e1'
            'fd8701cc0618b38c9290ab973f6947a41c0cfd661a71e63f09ba7b7c14382172'
            'd383ba54094826fbd7c9da37eefdabf0be770bf6bc9a998427162884dc8d0c94'
            '8edde9dffa07ead6bfc6277f145385b6152215144d5355c6e21911c32d0a869c'
            '3ca0be52a34ba3a7d30414ead4449d6faab71f88f7e439574ce7152b87c125bd')

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

