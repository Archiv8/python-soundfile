#!/bin/bash

# Based on the orginal packaging by Christopher Arndt <aur at chrisarndt dot de>
# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# [ToDo]: Add files: User documentation
# [ToDo]: Add files: Tooling
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/orgs/Archiv8/soundfile/discussions>
# Contributor: Ross Clark <https://github.com/orgs/Archiv8/soundfile/discussions>

_langname="python"
_relname="soundfile"
_casename="SoundFile"

pkgname="${_langname}-${_relname}"
pkgver=0.10.3.post1
pkgrel=3
pkgdesc="An audio library based on libsndfile, CFFI and NumPy"
url="https://github.com/bastibe/python-soundfile"
arch=(
  "any"
)
license=(
  "BSD"
)
makedepends=(
  # Arch Linux Official Repositories
  "python-setuptools"
)
depends=(
  # Arch Linux Official Repositories
  "python-cffi"
  "libsndfile"
  "python-numpy"
)
source=(
  "https://github.com/bastibe/python-soundfile/releases/download/${pkgver/\.post1/post1}/${_relname}-${pkgver}.tar.gz"
)
sha512sums=(
  "5087c8fb6891163677a1ad6ebdac650c32a739d600c2ce5fe344bdd79aaeff178afe2dd4f87ddcb7f99aaa3db47380424ac46fad51e2bcee812dacf49ed935d9"
)

build() {

  cd "${srcdir}/${_casename}-${pkgver}"

  python setup.py build
}

package() {

  cd "${srcdir}/${_casename}-${pkgver}"

  python setup.py install --root="${pkgdir}" --skip-build --optimize=1

  # install license
  install -Dm644 LICENSE -t "${pkgdir}"/usr/share/licenses/${pkgname}
}
