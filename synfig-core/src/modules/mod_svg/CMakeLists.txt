add_library(mod_svg MODULE
        "${CMAKE_CURRENT_LIST_DIR}/main.cpp"
        "${CMAKE_CURRENT_LIST_DIR}/layer_svg.cpp"
        "${CMAKE_CURRENT_LIST_DIR}/svg_parser.cpp"
)

target_include_directories(mod_svg
        SYSTEM PRIVATE
        ${GLIBMM_INCLUDE_DIRS}
        ${LIBXML_INCLUDE_DIRS}
)

target_link_libraries(mod_svg synfig ${LIBXML_LIBRARIES} ${GLIBMM_LIBRARIES})

install (
    TARGETS mod_svg
    DESTINATION lib/synfig/modules
)
