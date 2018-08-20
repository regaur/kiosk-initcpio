# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=kiosk-initcpio
pkgver=1.0
pkgrel=1
pkgdesc="Create initramfs for compressed, optionally encrupted, read-only root filesystem"
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

sha256sums=('40c68db597646b9a8c6f4720d81cb7e2f6715c6ff80e184bc84ad37fb4426563'
            'c48843008276fa620238d2562faeb3304cc4c41d1564800c77e8219164e758d0'
            '97276b0f511b782c0b7a61e2a626032b5d63ae4fd996d2a6ba901d0fadaf72f8'
            '7169d7d38b803bd0f95b437c92aacd1f22a6bd6e8a7ebb5a017e04b25f4fb5bf'
            'b40771a171b0b182b98670885340bdc12ca86f6eb2de8c565316091baf7ff3c8'
            'd4d86a5d4569ac497188ea1c85c39985433523d7268a31579f3b00aee180992b'
            '3c0becb0528360c465d4e6768cf5eb58896461be1f4888a697bbc252374a66f0'
            'fd8701cc0618b38c9290ab973f6947a41c0cfd661a71e63f09ba7b7c14382172'
            'd383ba54094826fbd7c9da37eefdabf0be770bf6bc9a998427162884dc8d0c94'
            '8edde9dffa07ead6bfc6277f145385b6152215144d5355c6e21911c32d0a869c'
            '3ca0be52a34ba3a7d30414ead4449d6faab71f88f7e439574ce7152b87c125bd')

package() {
  install -t /etc/mkinitcpio.d/ kiosk.preset
  install -t /etc/ mkinitcpio-kiosk-plymouth.conf
  install -t /etc/ mkinitcpio-kiosk.conf
  install -t /etc/initcpio/ archiso_shutdown
  install -t /etc/initcpio/hooks/ hooks-archiso_shutdown
  install -t /etc/initcpio/hooks/ hooks-archiso_loop_mnt
  install -t /etc/initcpio/hooks/ hooks-archiso
  install -t /etc/initcpio/install/ install-archiso_shutdown
  install -t /etc/initcpio/install/ install-archiso_kms
  install -t /etc/initcpio/install/ install-archiso_loop_mnt
  install -t /etc/initcpio/install/ install-archiso
}

