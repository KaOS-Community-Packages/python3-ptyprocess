license=("ISC")
arch=("any")
_pkgname=ptyprocess
pkgname=python3-${_pkgname}
pkgver=0.7.0
pkgrel=0
pkgdesc="Launch a subprocess in a pseudo terminal (pty), and interact with both the process and its pty."
url="https://github.com/pexpect/ptyprocess"
depends=("python3")
makedepends=("python3-setuptools")
source=(
"https://github.com/pexpect/${_pkgname}/archive/refs/tags/${pkgver}.tar.gz"
"LICENSE::https://raw.githubusercontent.com/pexpect/${_pkgname}/master/LICENSE"
)
sha512sums=(
"2ccba731cc3c17d1a942b319c7cbb894b69b4228b2141f30c845f4d64c9033bcdb2adaa735ebcdcf936bdb7124c0351a58cba614387325abacd683f256b705d9"
"77465d8319848ad6e4c3811276d6f7f5241f715d1f72012f155f5a1850abc6542fe7a74fcafc39d9801def60884d6d1acc4393700a552e44a05b763ae84970f0"
)

build() {
  cd ${_pkgname}-${pkgver}
  echo -e "#!/usr/bin/env python\n\nimport setuptools\nsetuptools.setup()\n" &> setup.py
  python3 setup.py build
}

package() {
  cd ${_pkgname}-${pkgver}
  python3 setup.py install --root="${pkgdir}" --optimize=1 --skip-build
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
