# Create library with the name: cmake_workshop_library
# Add the .cpp sources to it!
add_library(cmake_workshop_library ${CMAKE_CURRENT_LIST_DIR}/src/mqtt_lib.cpp)

# Add the include directory of the library to the cmake_workshop_library target
target_include_directories(cmake_workshop_library PUBLIC ${CMAKE_CURRENT_LIST_DIR}/inc/)

# Link the library with the rpi pico board sdk dependencies
target_link_libraries(cmake_workshop_library
        pico_cyw43_arch_lwip_poll
        pico_stdlib
        pico_lwip_mbedtls
        pico_mbedtls
        pico_lwip_mqtt)
