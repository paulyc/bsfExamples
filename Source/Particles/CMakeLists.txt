# Target
if(WIN32)
	add_executable(Particles WIN32 "Main.cpp")
else()
	add_executable(Particles "Main.cpp")
endif()
	
# Working directory
set_target_properties(Particles PROPERTIES VS_DEBUGGER_WORKING_DIRECTORY "$(OutDir)")		
	
# Libraries
## Local libs
target_link_libraries(Particles Common)

# Plugin dependencies
add_engine_dependencies(Particles)
add_dependencies(Particles bsfFBXImporter bsfFontImporter bsfFreeImgImporter)

# IDE specific
set_property(TARGET Particles PROPERTY FOLDER Examples)