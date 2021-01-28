# Script generated with import_catkin_packages.py
# For more information: https://github.com/bchretien/arch-ros-stacks
pkgdesc="ROS - MAVROS -- MAVLink extendable communication node for ROS with
proxy for Ground Control Station."
url='https://wiki.ros.org/mavros'

pkgname='ros-noetic-mavros'
pkgver='1.5.1'
arch=('i686' 'x86_64' 'aarch64' 'armv7h' 'armv6h')
pkgrel=1
license=('GPLv3, LGPLv3, BSD')

ros_makedepends=(
  ros-noetic-catkin
  ros-noetic-mavlink
  ros-noetic-angles
  ros-noetic-cmake-modules
)

makedepends=(
  cmake
  ros-build-tools
  ${ros_makedepends[@]}
  boost
  eigen
  geographiclib
)

ros_depends=(
  ros-noetic-diagnostic-updater
  ros-noetic-eigen-conversions
  ros-noetic-libmavconn
  ros-noetic-pluginlib
  ros-noetic-rosconsole-bridge
  ros-noetic-roscpp
  ros-noetic-tf2-ros
  ros-noetic-tf2-eigen
  ros-noetic-message-runtime
  ros-noetic-rospy
  ros-noetic-diagnostic-msgs
  ros-noetic-geometry-msgs
  ros-noetic-mavros-msgs
  ros-noetic-nav-msgs
  ros-noetic-geographic-msgs
  ros-noetic-trajectory-msgs
  ros-noetic-std-msgs
  ros-noetic-std-srvs
  ros-noetic-rosunit
)

depends=(
  ${ros_depends[@]}
  gtest
)

_dir="mavros-${pkgver}/mavros"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/mavlink/mavros/archive/${pkgver}.tar.gz")
sha256sums=('28e6b007bae627e6db5908575aa249f8fd081f18c67b9925a81914602296d33e')

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}
