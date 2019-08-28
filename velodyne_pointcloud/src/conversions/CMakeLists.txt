add_executable(cloud_node_vls cloud_node.cc convert.cc)
add_dependencies(cloud_node_vls ${${PROJECT_NAME}_EXPORTED_TARGETS})
target_link_libraries(cloud_node_vls velodyne_rawdata_vls
                      ${catkin_LIBRARIES} ${YAML_CPP_LIBRARIES})
install(TARGETS cloud_node_vls
        RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

add_library(cloud_nodelet_vls cloud_nodelet.cc convert.cc)
add_dependencies(cloud_nodelet_vls ${${PROJECT_NAME}_EXPORTED_TARGETS})
target_link_libraries(cloud_nodelet_vls velodyne_rawdata_vls
                      ${catkin_LIBRARIES} ${YAML_CPP_LIBRARIES})
install(TARGETS cloud_nodelet_vls
        RUNTIME DESTINATION ${CATKIN_GLOBAL_BIN_DESTINATION}
        ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
        LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION})

add_executable(ringcolors_node_vls ringcolors_node.cc colors.cc)
target_link_libraries(ringcolors_node_vls
                      ${catkin_LIBRARIES} ${YAML_CPP_LIBRARIES})
install(TARGETS ringcolors_node_vls
        RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

add_library(ringcolors_nodelet_vls ringcolors_nodelet.cc colors.cc)
target_link_libraries(ringcolors_nodelet_vls
                      ${catkin_LIBRARIES} ${YAML_CPP_LIBRARIES})
install(TARGETS ringcolors_nodelet_vls
        RUNTIME DESTINATION ${CATKIN_GLOBAL_BIN_DESTINATION}
        ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
        LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION})

add_executable(transform_node_vls transform_node.cc transform.cc)
add_dependencies(transform_node_vls ${${PROJECT_NAME}_EXPORTED_TARGETS})
target_link_libraries(transform_node_vls velodyne_rawdata_vls
                      ${catkin_LIBRARIES} ${YAML_CPP_LIBRARIES})
install(TARGETS transform_node_vls
        RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

add_library(transform_nodelet_vls transform_nodelet.cc transform.cc)
add_dependencies(transform_nodelet_vls ${${PROJECT_NAME}_EXPORTED_TARGETS})
target_link_libraries(transform_nodelet_vls velodyne_rawdata_vls
                      ${catkin_LIBRARIES} ${YAML_CPP_LIBRARIES})
install(TARGETS transform_nodelet_vls
        RUNTIME DESTINATION ${CATKIN_GLOBAL_BIN_DESTINATION}
        ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
        LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION})
