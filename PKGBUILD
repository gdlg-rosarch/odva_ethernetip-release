# Script generated with Bloom
pkgdesc="ROS - Library implementing ODVA EtherNet/IP (Industrial Protocol)."


pkgname='ros-melodic-odva-ethernetip'
pkgver='0.1.2_0'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'ros-melodic-catkin'
'ros-melodic-rosunit'
)

depends=('boost'
)

conflicts=()
replaces=()

_dir=odva_ethernetip
source=()
md5sums=()

prepare() {
    cp -R $startdir/odva_ethernetip $srcdir/odva_ethernetip
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/melodic/setup.bash ] && source /opt/ros/melodic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/melodic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

