# Script generated with Bloom
pkgdesc="ROS - This package provides a gui program as well as a rviz plugin to publish static transforms. Both support the transformation between various Euler angle representations. The rviz plugin also allows to configure the transform with an interactive marker."
url='http://wiki.ros.org/agni_tf_tools'

pkgname='ros-lunar-agni-tf-tools'
pkgver='0.1.0_2'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('eigen3'
'ros-lunar-catkin'
'ros-lunar-roscpp'
'ros-lunar-rviz'
'ros-lunar-tf2-ros'
)

depends=('ros-lunar-roscpp'
'ros-lunar-rviz'
'ros-lunar-tf2-ros'
)

conflicts=()
replaces=()

_dir=agni_tf_tools
source=()
md5sums=()

prepare() {
    cp -R $startdir/agni_tf_tools $srcdir/agni_tf_tools
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
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

