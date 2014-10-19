# Contributor: Jordan Anderson <aq@es.gy>

pkgname=sensu-bin
pkgver=0.14.0
deb_ver=0.14.0-1
pkgrel=2
pkgdesc="Omnibus version of Sensu, the open source monitoring framework. Direct from the .deb"
arch=('i686' 'x86_64')
license=('MPL' 'GPL' 'LGPL')
url="http://sensuapp.org/"

if [ "${CARCH}" = 'x86_64' ]; then
  ARCH='amd64'
md5sums=('a503600dc9ab2edccb8b274c3619fb6d')
elif [ "${CARCH}" = 'i686' ]; then
  ARCH='i386'
fi
install=sensu.install
source=("http://repos.sensuapp.org/apt/pool/sensu/main/s/sensu/sensu_${deb_ver}_${ARCH}.deb")

package() {
  tar xzvf ${srcdir}/data.tar.gz -C ${pkgdir}/
  msg2 "Cleaning up unwanted files..."
  rm -rv "${pkgdir}"/etc/init.d
  rm -rf "${pkgdir}"/opt/sensu/sv/sensu-dashboard
  mkdir "${pkgdir}"/usr/bin
  #cp "${pkgdir}"/opt/sensu/embedded/bin/sensu-ctl "${pkgdir}"/usr/bin/sensu-ctl
}
