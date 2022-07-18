#Maintainer: Dimm <dim320736@gmail.com>

pkgname=pantum-p2200series-driver
pkgver="1.1.84_1"
pkgrel=1
pkgdesc="Pantum P2200 series driver"
arch=('x86_64')
url="https://global.pantum.com"
license=('proprietary')
depends=('cups')
makedepends=('unzip')
_basename="PantumUbuntuDriverV${pkgver/_/-}_1644310280716"
_zipname="${_basename}.zip"

source=(
	"https://drivers.pantum.com/userfiles/files/download/${_zipname}"
)
md5sums=('1343c21c2aa5db6cf0ee4499b6a7188f')

build() {
	cd ${srcdir}

	unzip -p ${_zipname} | bsdtar -xf "Pantum Ubuntu Driver V1.1.84-1/Resources/pantum_${pkgver/_/-}_amd64.deb"
	ar x 'Pantum Ubuntu Driver V1.1.84-1'/Resources/pantum_${pkgver/_/-}_amd64.deb data.tar.xz
        mkdir -p ${pkgname}-${pkgver/_/-}
	bsdtar -xf data.tar.xz -C ${pkgname}-${pkgver/_/-}
	       
}

package() {
	cd ${pkgdir}
	cp -a ${srcdir}/${pkgname}-${pkgver/_/-}/* .

}

