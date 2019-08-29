# build the driver node
add_executable(velodyne_node_vls velodyne_node.cc driver.cc)
add_dependencies(velodyne_node_vls velodyne_driver_vls_gencfg)
target_link_libraries(velodyne_node_vls
  velodyne_input_vls
  ${catkin_LIBRARIES}
  ${libpcap_LIBRARIES}
)

# build the nodelet version
add_library(driver_nodelet_vls nodelet.cc driver.cc)
add_dependencies(driver_nodelet_vls velodyne_driver_vls_gencfg)
target_link_libraries(driver_nodelet_vls
  velodyne_input_vls
  ${catkin_LIBRARIES}
  ${libpcap_LIBRARIES}
)

# install runtime files
install(TARGETS velodyne_node_vls
        RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
        COMPONENT main
)
install(TARGETS driver_nodelet_vls
        LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
)
