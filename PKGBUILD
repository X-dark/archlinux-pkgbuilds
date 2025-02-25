# Contributor: Richard PALO <richard.palo@free.fr>
pkgname=python-schwifty
_name=${pkgname#python-}
pkgver=2024.11.0
pkgrel=3
pkgdesc="Validate/generate IBANS and BICS"
arch=('any')
url="http://github.com/mdomke/schwifty"
license=('MIT')
makedepends=('python-build' 'python-installer' 'python-wheel' 'python-hatchling' 'python-hatch-vcs')
optdepends=('python-pydantic>=2.0: data validation')
depends=('python>=3.9' 'python-iso3166' 'python-pycountry' 'python-rstr')
source=(https://files.pythonhosted.org/packages/source/${_name::1}/${_name}/${_name}-${pkgver}.tar.gz)
sha256sums=('d0aaed03168403b433de515d663df09516941ae70152850da3afe3c242255f6a')

build() {
  cd "$srcdir/$_name-$pkgver"
  python -m build --wheel --no-isolation
}

package() {
  cd "$srcdir/$_name-$pkgver"
  python -m installer --destdir="$pkgdir" dist/*.whl
  install -Dm644 "${srcdir}/${_name}-${pkgver}/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
