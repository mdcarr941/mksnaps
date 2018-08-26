# Maintainer:  Matthew Carr  <mdcarr941 at gmail dot com>

pkgname=mksnaps
pkgver=0.1
pkgrel=1
pkgdesc='A systemd target to take snapshots of btrfs or lvm file systems.'
arch=('i686' 'x86_64')
license=('GPLv3')
depends=('systemd')
#url=''
#checkdepends=('')
optdepends=('grub')
source=(
  'mksnaps.conf'
  'mksnaps.cfg'
  'mksnaps.target'
  'mksnaps-btrfs'
  'mksnaps-btrfs.service'
  'mksnaps-lvm'
  'mksnaps-lvm.service'
)
sha256sums=('6314a3e63610683e34716714d58c375d1c20c5f53b1040a4eb8d6b167284df0a'
            '3be02785ed16c648311b76865279c4976b7da738e789de7dab03e99f1b4b158f'
            '5583fb11cdbc9f4fc6d74a800a88467db7c87b05a3ba21624da87bfba0ab7e6b'
            'b1a6c731756b28374327c05ca8eb36c8a040e0977337fd71b1e7f4d2b6463f09'
            'f17067c6fac6fae0a816710a728077fa2d3428adfe396431608d4bfd56f43d52'
            '3c8e07c86a6a1c6885bd53e577af685b92ab37ce9853d4dad662fe47c58d72f6'
            'a7337d931448b62e3c3f538d4170a1262179700e98a6049818c7ccaa5da8993b')
backup=('etc/mksnaps.conf' 'boot/grub/mksnaps.cfg')

package() {
  install -Dm644 mksnaps.conf "$pkgdir/etc/mksnaps.conf"
  install -Dm644 mksnaps.cfg "$pkgdir/boot/grub/mksnaps.cfg"
  for file in mksnaps-btrfs mksnaps-lvm; do
    install -Dm744 "$file" "$pkgdir/usr/bin/$file"
  done
  for file in mksnaps.target mksnaps-btrfs.service mksnaps-lvm.service; do
    install -Dm644 $file "$pkgdir/usr/lib/systemd/system/$file"
  done
}
