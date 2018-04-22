# Script generated with Bloom
pkgdesc="ROS - ProAut octomap package"


pkgname='ros-kinetic-octomap-pa'
pkgver='1.3.3_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('pcl'
'ros-kinetic-catkin'
'ros-kinetic-geometry-msgs'
'ros-kinetic-laser-geometry'
'ros-kinetic-message-generation'
'ros-kinetic-nav-msgs'
'ros-kinetic-octomap-msgs'
'ros-kinetic-octomap-ros'
'ros-kinetic-parameter-pa'
'ros-kinetic-pcl-conversions'
'ros-kinetic-pcl-ros'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-tf'
)

depends=('pcl'
'ros-kinetic-geometry-msgs'
'ros-kinetic-laser-geometry'
'ros-kinetic-message-runtime'
'ros-kinetic-nav-msgs'
'ros-kinetic-octomap-msgs'
'ros-kinetic-octomap-ros'
'ros-kinetic-parameter-pa'
'ros-kinetic-pcl-conversions'
'ros-kinetic-pcl-ros'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-tf'
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
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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

