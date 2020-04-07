disable_rtti()

INCLUDE_DIRECTORIES("../bass/c")
LINK_DIRECTORIES("../bass/c")

file(GLOB_RECURSE SOURCES *.cpp *.h)

new_library_shared(mod_audio "${SOURCES}" "")
if(WIN32)
target_link_libraries(mod_audio bass)
endif()
set_target_properties(mod_audio PROPERTIES FOLDER modules)