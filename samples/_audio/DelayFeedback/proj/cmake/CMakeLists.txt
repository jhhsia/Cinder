cmake_minimum_required( VERSION 2.8 FATAL_ERROR )
set( CMAKE_VERBOSE_MAKEFILE ON )

project( audio-DelayFeedback )

get_filename_component( CINDER_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../../../../.." ABSOLUTE )
get_filename_component( APP_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../../" ABSOLUTE )

include( "${CINDER_PATH}/proj/cmake/modules/cinderMakeApp.cmake" )

set( RESOURCE_FILES RESOURCES
	${APP_PATH}/resources/smoothCircle.vert
	${APP_PATH}/resources/smoothCircle.frag
)

ci_make_app(
	SOURCES     ${APP_PATH}/src/DelayFeedbackApp.cpp
	CINDER_PATH ${CINDER_PATH}
	INCLUDES    ${APP_PATH}/include
	RESOURCES   ${RESOURCE_FILES}
)
