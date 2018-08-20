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

