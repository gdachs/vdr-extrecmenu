# Maintainer: Christopher Reimer <c[dot]reimer[at]googlemail[dot]com>
pkgname=vdr-extrecmenu
pkgver=20121221
_gitver=16da1f90
_vdrapi=1.7.35
pkgrel=2yavdr1
pkgdesc="provides additional functions to VDR's recordings menu"
url="http://projects.vdr-developer.org/projects/show/plg-extrecmenu"
arch=('x86_64' 'i686')
license=('GPL2')
depends=('gcc-libs' "vdr-api=${_vdrapi}")
optdepends=()
_plugname=$(echo $pkgname | sed 's/vdr-//g')
replaces=("vdr-plugin-$_plugname")
conflicts=("vdr-plugin-$_plugname")
source=("http://projects.vdr-developer.org/git/vdr-plugin-$_plugname.git/snapshot/vdr-plugin-$_plugname-$_gitver.tar.bz2")
md5sums=('afac708613deffb87d8d8d29c923513c')

package() {
  cd "${srcdir}/vdr-plugin-${_plugname}-${_gitver}"

  mkdir -p $pkgdir/usr/lib/vdr/plugins
  make CFLAGS="$(pkg-config vdr --variable=cflags)" \
       CXXFLAGS="$(pkg-config vdr --variable=cxxflags)" \
       VDRDIR="/usr/include/vdr" \
       LIBDIR="$pkgdir/$(pkg-config vdr --variable=libdir)" \
       LOCALEDIR="$pkgdir/$(pkg-config vdr --variable=locdir)"
}
