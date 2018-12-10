pkgbase=python3-ptyprocess
pkgname=(python3-ptyprocess)
_pkgname=ptyprocess
pkgver=0.6.0
pkgrel=1
pkgdesc="Launch a subprocess in a pseudo terminal (pty), and interact with both the process and its pty."
url="https://github.com/pexpect/ptyprocess"
arch=('any')
license=('ISC')
depends=('python3')
makedepends=('python3-setuptools')
source=("https://pypi.io/packages/source/p/$_pkgname/$_pkgname-$pkgver.tar.gz"
        "LIC-pty-$pkgver::https://raw.githubusercontent.com/pexpect/ptyprocess/master/LICENSE")
sha512sums=('b34b6bca977f09d1443b210e338e1300e12d6ef35857f9543b3a116ef3b500ad4844357a7a283321756f886af41bddb1f02b27bf200ef1e82a96fd9e431bed86'
            '0847180ae31aeae060c4f127f640d7501eea6285ccfd495f032cfcb09058a0ebfff55b75c8d005aa0d73e6401f61d8203c684f4002775436db1d5599aaba937d')

prepare() {
  cd "$srcdir"
  mv "LIC-pty-$pkgver" LICENSE
}

package_python3-ptyprocess() {
  cd "$srcdir/$_pkgname-$pkgver"
  python3 setup.py install --root="$pkgdir/" --prefix=/usr --optimize=0
  install -Dm644 "$srcdir/LICENSE" "$pkgdir/usr/share/licenses/python-$_pkgname/LICENSE"
}
