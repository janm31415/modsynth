
set(HDRS
modsynth.hpp
)
	
set(SRCS
modsynth.cpp
example.cpp
)

# general build definitions
add_definitions(-D_SCL_SECURE_NO_WARNINGS)
add_definitions(-D_CRT_SECURE_NO_WARNINGS)

add_definitions(-DMEMORY_LEAK_TRACKING)
add_definitions(-D_USE_MATH_DEFINES)

add_executable(ModSynth ${HDRS} ${SRCS})
source_group("Header Files" FILES ${hdrs})
source_group("Source Files" FILES ${srcs})

target_include_directories(ModSynth
    PRIVATE
	  ${CMAKE_CURRENT_SOURCE_DIR}/../
    ${CMAKE_CURRENT_BINARY_DIR}/../sdl2/include
    )
	
target_link_libraries(ModSynth
    PRIVATE
    SDL2-static
    SDL2main
    )
