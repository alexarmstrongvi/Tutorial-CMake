message( "INFO :: Generating build files for project located at ${CMAKE_CURRENT_SOURCE_DIR}" )
message( "INFO :: Build files stored at :: ${CMAKE_CURRENT_BINARY_DIR}" )

cmake_minimum_required( VERSION 3.15 )

Project( 03_simple_project_structure 
        VERSION # major.minor.patch.tweak
            1.0.0.0
        LANGUAGES
            CXX
)
message( STATUS "Project defined : ${PROJECT_NAME} (version ${PROJECT_VERSION})" )

# Create a library target for this project
add_library( 03_simple_project_structureLib
    # List source files in src/
    src/adder.cxx
    # List header files in include/ (optional but helpful)
    include/03_simple_project_structure/adder.h
)
# Add directories to the library so that files are useable
target_include_directories(03_simple_project_structureLib 
    PUBLIC # any projects linking this library will require these files too 
        include
)

# Create an executable target
add_executable( add_and_print apps/add_and_print.cxx )
# Link all needed libraries for the executable
target_link_libraries( add_and_print 
    PUBLIC 03_simple_project_structureLib        
)
