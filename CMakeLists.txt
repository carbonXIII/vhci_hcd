cmake_minimum_required(VERSION 3.11)
project(vhci_hcd)

ExternalProject_add(vhci_hcd_make
  SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}
  CONFIGURE_COMMAND ""
  BUILD_COMMAND ${CMAKE_COMMAND} -E env CC=${CMAKE_C_COMPILER} make -C <SOURCE_DIR>
  BUILD_IN_SOURCE TRUE
  INSTALL_COMMAND ""
  )

add_library(vhci_hcd INTERFACE)
target_include_directories(vhci_hcd INTERFACE ${CMAKE_SOURCE_DIR})
add_library(vhci_hcd::vhci_hcd ALIAS vhci_hcd)
