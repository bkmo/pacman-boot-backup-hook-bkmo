# Maintainer: Markus Schanz <coksnuss@googlemail.com>
pkgname=pacman-boot-backup-hook-bkmo
pkgver=1.6.0
pkgrel=1
pkgdesc="Pacman hook that creates a copy of the /boot directory prior and post to upgrades of the systemd package or when mkinitcpio is triggered."
install=$pkgname.install
arch=('any')
license=('MIT')
changelog=CHANGELOG
conflicts=('pacman-boot-backup-hook')
source=('LICENSE'
        'backup-boot-partition'
        '0-bootbackup.hook'
        'uu_bootbackup.hook'
        'pacman-boot-backup.conf')
md5sums=('ac9ac34b11dd5a53d096a734ab677479'
         'SKIP'
         'SKIP'
         'SKIP'
         'SKIP')

package() {
	install -m 0755 -d $pkgdir/usr/share/licenses/$pkgname
	install -m 0644 $srcdir/LICENSE $pkgdir/usr/share/licenses/$pkgname

	install -m 0755 -d $pkgdir/etc
	install -m 0644 $srcdir/pacman-boot-backup.conf $pkgdir/etc

	install -m 0755 -d $pkgdir/usr/share/libalpm/hooks
	install -m 0644 $srcdir/0-bootbackup.hook $pkgdir/usr/share/libalpm/hooks
	install -m 0644 $srcdir/uu_bootbackup.hook $pkgdir/usr/share/libalpm/hooks

	install -m 0755 -d $pkgdir/usr/share/libalpm/scripts
	install -m 0755 $srcdir/backup-boot-partition $pkgdir/usr/share/libalpm/scripts
}
