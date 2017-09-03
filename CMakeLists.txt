cmake_minimum_required(VERSION 2.8)

project(vorbis)

#add_definitions(-Wall -Wcast-qual -Wextra -Wshadow -fno-exceptions -fno-rtti -pedantic -flto -m64)

include_directories(../ogg/include)
include_directories(include)
include_directories(lib)

foreach(f analysis.c bitrate.c block.c codebook.c envelope.c floor0.c floor1.c info.c lookup.c lpc.c lsp.c mapping0.c mdct.c psy.c registry.c res0.c sharedbook.c smallft.c synthesis.c vorbisenc.c vorbisfile.c window.c)
	list(APPEND sourceFiles "lib/${f}")
endforeach()

add_library(vorbis STATIC ${sourceFiles} ${headerFiles})
