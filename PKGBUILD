# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Contributor: David Manouchehri

_proj="vim"
_pkg="javascript"
_pkgname="${_proj}-${_pkg}"
pkgname="${_pkgname}"
_branch="master"
pkgver=1.2.2.r582.gc470ce1
_commit='c470ce1399a544fe587eab950f571c83cccfbbdc'
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
_tag_name="commit"
_tag="${_commit}"
_tag_name="branch"
_tag="${_branch}"
source=(
  "git+${url}.git#${_tag_name}=${_tag}"
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
