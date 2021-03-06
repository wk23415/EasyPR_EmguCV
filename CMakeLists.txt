cmake_minimum_required(VERSION 2.6)

project (EasyPR)

list(APPEND CMAKE_CXX_FLAGS "-std=c++0x")

find_package(OpenCV REQUIRED)

set(CMAKE_SOURCE_DIR ./src)

include_directories(${CMAKE_SOURCE_DIR}/include/)

set(SOURCE_FILES
	src/main.cpp
	src/core/chars_identify.cpp
	src/core/chars_recognise.cpp
	src/core/chars_segment.cpp
	src/core/features.cpp
	src/core/plate_detect.cpp
	src/core/plate_judge.cpp
	src/core/plate_locate.cpp
	src/core/plate_recognize.cpp
	src/test/accuracy_test.cpp
	src/test/test.cpp
	src/train/ann_train.cpp
	src/train/svm_train.cpp
	src/util/deface.cpp
	src/util/general_test_prepare.cpp
	src/util/generate_gdts.cpp
	src/util/learn_prepare.cpp
	src/util/mc_data_prepare.cpp
	src/util/util.cpp
	src/util/CParser.cpp
)

add_executable(EasyPR ${SOURCE_FILES})
target_link_libraries(EasyPR ${OpenCV_LIBS})
