# Script generated with Bloom
pkgdesc="ROS - Package for TurtleBot3 fake node. With this package, simple tests can be done without a robot. You can do simple tests using this package on rviz without real robots."
url='http://turtlebot3.robotis.com'

pkgname='ros-kinetic-turtlebot3-fake'
pkgver='0.2.4_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-geometry-msgs'
'ros-kinetic-nav-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-tf'
'ros-kinetic-turtlebot3-msgs'
)

depends=('ros-kinetic-geometry-msgs'
'ros-kinetic-nav-msgs'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-tf'
'ros-kinetic-turtlebot3-msgs'
)

conflicts=()
replaces=()

_dir=turtlebot3_fake
source=()
md5sums=()

prepare() {
    cp -R $startdir/turtlebot3_fake $srcdir/turtlebot3_fake
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

