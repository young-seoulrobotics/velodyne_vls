add_library(velodyne_input_vls input.cc)
target_link_libraries(velodyne_input_vls
  ${catkin_LIBRARIES}
  ${libpcap_LIBRARIES}
)
if(catkin_EXPORTED_TARGETS)
  add_dependencies(velodyne_input_vls ${catkin_EXPORTED_TARGETS})
endif()

install(TARGETS velodyne_input_vls
        LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
)
