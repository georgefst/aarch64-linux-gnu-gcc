# Maintainer: George Thomas <georgefsthomas@gmail.com>

target=aarch64-none-linux-gnu
pkgver=10.3
pkgrel=2021.07
pkgverfull=${pkgver}-${pkgrel}
pkgname=${target}-gcc-${pkgver}-bin
pkgdesc="GNU Cross Compilation Toolchain for AArch64 (GCC ${pkgver})"
arch=('x86_64')
url="https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-a/downloads"
license=('GPL' 'LGPL')
depends=(binutils)
conflicts=('aarch64-linux-gnu-gcc')
options=(!emptydirs !strip staticlibs)
source=("https://developer.arm.com/-/media/Files/downloads/gnu-a/${pkgverfull}/binrel/gcc-arm-${pkgverfull}-x86_64-${target}.tar.xz")
md5sums=(07bbe2b5277b75ba36a924e9136366a4)

package() {
  mkdir -p ${pkgdir}/usr
  cp -a ${srcdir}/gcc-arm-${pkgverfull}-x86_64-${target}/* ${pkgdir}/usr

  rm -f ${pkgdir}/usr/*-manifest.txt
  rm -rf ${pkgdir}/usr/lib64
  rm -rf ${pkgdir}/usr/include
  rm -rf ${pkgdir}/usr/share/{doc,gcc-*,gdb,info,locale}
  rm -rf ${pkgdir}/usr/share/man/{man5,man7}
  rm -rf ${pkgdir}/usr/lib/bfd-plugins/libdep.so
}
