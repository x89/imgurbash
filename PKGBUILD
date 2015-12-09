# Maintainer: Andrey Vihrov <andrey.vihrov at gmail.com>
# Contributor: Jan Stępień <jstepien@users.sourceforge.net>
# Contributor: David Trail <david@vaunt.eu>

pkgname=imgurbash
pkgver=4
pkgrel=3
pkgdesc="A simple bash script to upload an image to imgur from the commandline"
arch=('any')
url="https://imgur.com/tools/"
license=('custom:PublicDomain')
depends=('curl')
optdepends=('xsel: automatically putting the URL on the X selection for easy pasting'
	'xclip: an alternative to xsel')
source=("https://imgur.com/tools/imgurbash.sh"
        "https://raw.githubusercontent.com/x89/imgurbash/master/https.diff")
sha256sums=('41310047e634c4be5471d0470b7e862b7f27158fdc6afd2fc1a17fbc8b6da79a'
            '95f78d865b5ef588ba32b6619223e1642f1884e5cb537b7dd845109f0b474a50')

package() {
  cd "${srcdir}"
  patch --follow-symlinks imgurbash.sh < https.diff
  install -D -m 755 imgurbash.sh "${pkgdir}/usr/bin/imgurbash"

  mkdir -p "${pkgdir}/usr/share/licenses/${pkgname}"
  sed -n '/imgur script/,/you will./p' imgurbash.sh \
    > "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

# vim:set ts=2 sw=2 et:
