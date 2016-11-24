cmake_minimum_required(VERSION 3.0)

project(ActiveContour)
list( APPEND CMAKE_CXX_FLAGS "-std=c++0x ${CMAKE_CXX_FLAGS}")

# set(CMAKE_LIBRARY_PATH "C:\\Program Files (x86)\\Windows Kits\\8.0\\Lib\\win8\\um\\x64")

# add_definitions(-DNOMINMAX)

# Find OpenCV
find_package( OpenCV REQUIRED )

# find_package(Qt5Widgets REQUIRED)
# set(CMAKE_AUTOMOC ON)


include_directories(
  ${CMAKE_CURRENT_BINARY_DIR}
  ${CMAKE_CURRENT_SOURCE_DIR}/include
  ${CMAKE_CURRENT_SOURCE_DIR}/src
)

file(GLOB HEADER_FILES include/*.h)
file(GLOB CXX_FILES src/*.cpp)

# file(GLOB UI_FILES src/*.ui)
# qt5_wrap_ui(UISrcs ${UI_FILES} )

add_executable(ActiveContour
		${CXX_FILES} 
		${HEADER_FILES} 
		# ${UISrcs}
)

# qt5_use_modules(arius Core Gui Widgets)

target_link_libraries(ActiveContour
    ${OpenCV_LIBS}
)