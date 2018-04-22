# Script generated with Bloom
pkgdesc="ROS - ProAut octomap package"


pkgname='ros-lunar-octomap-pa'
pkgver='1.3.3_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('pcl'
'ros-lunar-catkin'
'ros-lunar-geometry-msgs'
'ros-lunar-laser-geometry'
'ros-lunar-message-generation'
'ros-lunar-nav-msgs'
'ros-lunar-octomap-msgs'
'ros-lunar-octomap-ros'
'ros-lunar-parameter-pa'
'ros-lunar-pcl-conversions'
'ros-lunar-pcl-ros'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'ros-lunar-std-srvs'
'ros-lunar-tf'
)

depends=('pcl'
'ros-lunar-geometry-msgs'
'ros-lunar-laser-geometry'
'ros-lunar-message-runtime'
'ros-lunar-nav-msgs'
'ros-lunar-octomap-msgs'
'ros-lunar-octomap-ros'
'ros-lunar-parameter-pa'
'ros-lunar-pcl-conversions'
'ros-lunar-pcl-ros'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-std-msgs'
'ros-lunar-std-srvs'
'ros-lunar-tf'
)

conflicts=()
replaces=()

_dir=octomap_pa
source=()
md5sums=()

prepare() {
    cp -R $startdir/octomap_pa $srcdir/octomap_pa
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

