cmake_minimum_required(VERSION 3.21)

project(rtmp)

list(APPEND RTMP_SOURCES 
			librtmp/amf.c
			librtmp/log.c
			librtmp/parseurl.c
			librtmp/rtmp.c
			minirtmp.c
			minirtmp_player.c
			minirtmp_test.c
			system.c)

add_executable(rtmp ${RTMP_SOURCES})
target_link_libraries(rtmp WS2_32.lib)
set_target_properties(rtmp PROPERTIES FOLDER "rtmp"
									      LINKER_LANGUAGE CXX)
