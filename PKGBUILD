# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Contributor: David Manouchehri

_proj="vim"
_pkg="javascript"
_pkgname="${_proj}-${_pkg}"
pkgname="${_pkgname}-git"
_branch=master
pkgver=0.1.0.r4.ge628cba
pkgrel=1
pkgdesc="Vastly improves Vim's JavaScript indentation"
arch=(
  'any'
)
_http="https://github.com"
_ns="pangloss"
url="${_http}/${_ns}/${_pkgname}"
license=(
  'custom:vim'
)
depends=(
  "${_proj}"
)
makedepends=(
  'git'
)
provides=(
  "${_pkgname}=${pkgver}"
)
conflicts=(
  "${_pkgname}"
)
source=(
  "git+${url}.git#branch=${_branch}"
)
sha512sums=(
  'SKIP'
)

pkgver() {
  cd \
    "${srcdir}/${_pkgname}"
  git \
    describe \
      --long | \
    sed \
      's/\([^-]*-g\)/r\1/;s/-/./g' | \
      cut \
        -c \
	2-
}

package() {
  cd \
    "${srcdir}/${_pkgname}"
  install \
    -dm755 \
    "${pkgdir}/usr/share/${_proj}/vimfiles"
  find \
    * \
    -maxdepth \
      0 \
    -type \
      d \
    -exec \
      cp \
        -R \
	-t \
	"${pkgdir}/usr/share/vim/vimfiles" \
	'{}' \
	\+
}
