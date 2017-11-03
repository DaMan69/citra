set(SRCS
            ../audio_core/audio_core.cpp
            ../audio_core/codec.cpp
            ../audio_core/hle/dsp.cpp
            ../audio_core/hle/filter.cpp
            ../audio_core/hle/mixers.cpp
            ../audio_core/hle/pipe.cpp
            ../audio_core/hle/source.cpp
            ../audio_core/interpolate.cpp
            ../audio_core/sink_details.cpp
            ../audio_core/time_stretch.cpp
            )

set(HEADERS
            ../audio_core/audio_core.h
            ../audio_core/codec.h
            ../audio_core/hle/common.h
            ../audio_core/hle/dsp.h
            ../audio_core/hle/filter.h
            ../audio_core/hle/mixers.h
            ../audio_core/hle/pipe.h
            ../audio_core/hle/source.h
            ../audio_core/interpolate.h
            ../audio_core/null_sink.h
            ../audio_core/sink.h
            ../audio_core/sink_details.h
            ../audio_core/time_stretch.h
            )

if(SDL2_FOUND)
    set(SRCS ${SRCS} ../audio_core/sdl2_sink.cpp)
    set(HEADERS ${HEADERS} ../audio_core/sdl2_sink.h)
endif()

create_directory_groups(${SRCS} ${HEADERS})

add_library(audio_core STATIC ${SRCS} ${HEADERS})
target_link_libraries(audio_core PUBLIC common core)
target_link_libraries(audio_core PRIVATE SoundTouch)

if(SDL2_FOUND)
    target_link_libraries(audio_core PRIVATE SDL2)
    target_compile_definitions(audio_core PRIVATE HAVE_SDL2)
endif()
