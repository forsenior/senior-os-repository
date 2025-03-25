pkgbase=python-sapps
pkgname=(python-sconf python-sweb python-smail python-srun)
pkgver=`date +%Y%m%d%H`
pkgrel=1
pkgdesc="Python SeniorOS apps package"
arch=('any')
url="https://github.com/forsenior/senior-os"
source_url="https://github.com/forsenior/senior-os.git"
license=('mit')
depends=(python python-pyqt5 python-dataclass-wizard python-validate-email python-pillow python-pyqt5-webengine python-screeninfo python-requests python-chardet python-vcolorpicker python-qtpy python-joblib python-pycryptodome)
source=("git+""$source_url")
sha256sums=('SKIP')

makedepends=(python-poetry)

build() {
    cd "${srcdir}/senior-os/sconf"
    python -m build --wheel --no-isolation
    cd "${srcdir}/senior-os/smail"
    python -m build --wheel --no-isolation
    cd "${srcdir}/senior-os/sweb"
    python -m build --wheel --no-isolation
    cd "${srcdir}/senior-os/srun"
    python -m build --wheel --no-isolation
}

package_python-sconf() {
    cd "${srcdir}/senior-os/sconf"
    python -m installer --destdir="$pkgdir" dist/*.whl
}

package_python-sweb() {
    cd "${srcdir}/senior-os/sweb"
    python -m installer --destdir="$pkgdir" dist/*.whl
}

package_python-smail(){
    cd "${srcdir}/senior-os/smail"
    python -m installer --destdir="$pkgdir" dist/*.whl
}

package_python-srun(){
    cd "${srcdir}/senior-os/srun"
    python -m installer --destdir="$pkgdir" dist/*.whl
}
