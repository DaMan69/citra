set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${PROJECT_SOURCE_DIR}/CMakeModules)

set(SRCS
            configuration/config.cpp
            configuration/configure_audio.cpp
            configuration/configure_debug.cpp
            configuration/configure_dialog.cpp
            configuration/configure_general.cpp
            configuration/configure_graphics.cpp
            configuration/configure_input.cpp
            configuration/configure_system.cpp
            configuration/configure_web.cpp
            debugger/graphics/graphics.cpp
            debugger/graphics/graphics_breakpoint_observer.cpp
            debugger/graphics/graphics_breakpoints.cpp
            debugger/graphics/graphics_cmdlists.cpp
            debugger/graphics/graphics_surface.cpp
            debugger/graphics/graphics_tracing.cpp
            debugger/graphics/graphics_vertex_shader.cpp
            debugger/profiler.cpp
            debugger/registers.cpp
            debugger/wait_tree.cpp
            updater/updater.cpp
            util/spinbox.cpp
            util/util.cpp
            aboutdialog.cpp
            bootmanager.cpp
            game_list.cpp
            hotkeys.cpp
            main.cpp
            ui_settings.cpp
            citra-qt.rc
            Info.plist
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
            ../audio_core/sdl2_sink.cpp
            ../video_core/command_processor.cpp
            ../video_core/debug_utils/debug_utils.cpp
            ../video_core/geometry_pipeline.cpp
            ../video_core/pica.cpp
            ../video_core/primitive_assembly.cpp
            ../video_core/regs.cpp
            ../video_core/renderer_base.cpp
            ../video_core/renderer_opengl/gl_rasterizer.cpp
            ../video_core/renderer_opengl/gl_rasterizer_cache.cpp
            ../video_core/renderer_opengl/gl_shader_gen.cpp
            ../video_core/renderer_opengl/gl_shader_util.cpp
            ../video_core/renderer_opengl/gl_state.cpp
            ../video_core/renderer_opengl/renderer_opengl.cpp
            ../video_core/shader/shader.cpp
            ../video_core/shader/shader_interpreter.cpp
            ../video_core/swrasterizer/clipper.cpp
            ../video_core/swrasterizer/framebuffer.cpp
            ../video_core/swrasterizer/lighting.cpp
            ../video_core/swrasterizer/proctex.cpp
            ../video_core/swrasterizer/rasterizer.cpp
            ../video_core/swrasterizer/swrasterizer.cpp
            ../video_core/swrasterizer/texturing.cpp
            ../video_core/texture/etc1.cpp
            ../video_core/texture/texture_decode.cpp
            ../video_core/vertex_loader.cpp
            ../video_core/video_core.cpp
            ../video_core/shader/shader_jit_x64.cpp
            ../video_core/shader/shader_jit_x64_compiler.cpp
            )

set(HEADERS
            configuration/config.h
            configuration/configure_audio.h
            configuration/configure_debug.h
            configuration/configure_dialog.h
            configuration/configure_general.h
            configuration/configure_graphics.h
            configuration/configure_input.h
            configuration/configure_system.h
            configuration/configure_web.h
            debugger/graphics/graphics.h
            debugger/graphics/graphics_breakpoint_observer.h
            debugger/graphics/graphics_breakpoints.h
            debugger/graphics/graphics_breakpoints_p.h
            debugger/graphics/graphics_cmdlists.h
            debugger/graphics/graphics_surface.h
            debugger/graphics/graphics_tracing.h
            debugger/graphics/graphics_vertex_shader.h
            debugger/profiler.h
            debugger/registers.h
            debugger/wait_tree.h
            updater/updater.h
            updater/updater_p.h
            util/spinbox.h
            util/util.h
            aboutdialog.h
            bootmanager.h
            game_list.h
            game_list_p.h
            hotkeys.h
            main.h
            ui_settings.h
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
            ../audio_core/sdl2_sink.h
            ../video_core/command_processor.h
            ../video_core/debug_utils/debug_utils.h
            ../video_core/geometry_pipeline.h
            ../video_core/gpu_debugger.h
            ../video_core/pica.h
            ../video_core/pica_state.h
            ../video_core/pica_types.h
            ../video_core/primitive_assembly.h
            ../video_core/rasterizer_interface.h
            ../video_core/regs.h
            ../video_core/regs_framebuffer.h
            ../video_core/regs_lighting.h
            ../video_core/regs_pipeline.h
            ../video_core/regs_rasterizer.h
            ../video_core/regs_shader.h
            ../video_core/regs_texturing.h
            ../video_core/renderer_base.h
            ../video_core/renderer_opengl/gl_rasterizer.h
            ../video_core/renderer_opengl/gl_rasterizer_cache.h
            ../video_core/renderer_opengl/gl_resource_manager.h
            ../video_core/renderer_opengl/gl_shader_gen.h
            ../video_core/renderer_opengl/gl_shader_util.h
            ../video_core/renderer_opengl/gl_state.h
            ../video_core/renderer_opengl/pica_to_gl.h
            ../video_core/renderer_opengl/renderer_opengl.h
            ../video_core/shader/debug_data.h
            ../video_core/shader/shader.h
            ../video_core/shader/shader_interpreter.h
            ../video_core/swrasterizer/clipper.h
            ../video_core/swrasterizer/framebuffer.h
            ../video_core/swrasterizer/lighting.h
            ../video_core/swrasterizer/proctex.h
            ../video_core/swrasterizer/rasterizer.h
            ../video_core/swrasterizer/swrasterizer.h
            ../video_core/swrasterizer/texturing.h
            ../video_core/texture/etc1.h
            ../video_core/texture/texture_decode.h
            ../video_core/utils.h
            ../video_core/vertex_loader.h
            ../video_core/video_core.h
            ../video_core/shader/shader_jit_x64.h
            ../video_core/shader/shader_jit_x64_compiler.h
            )

set(UIS
            configuration/configure.ui
            configuration/configure_audio.ui
            configuration/configure_debug.ui
            configuration/configure_general.ui
            configuration/configure_graphics.ui
            configuration/configure_input.ui
            configuration/configure_system.ui
            configuration/configure_web.ui
            debugger/registers.ui
            aboutdialog.ui
            hotkeys.ui
            main.ui
            )

file(GLOB_RECURSE ICONS ${CMAKE_SOURCE_DIR}/dist/icons/*)
file(GLOB_RECURSE THEMES ${CMAKE_SOURCE_DIR}/dist/qt_themes/*)

create_directory_groups(${SRCS} ${HEADERS} ${UIS})

if (Qt5_FOUND)
    qt5_wrap_ui(UI_HDRS ${UIS})
else()
    qt4_wrap_ui(UI_HDRS ${UIS})
endif()

if (APPLE)
    set(MACOSX_ICON "../../dist/citra.icns")
    set_source_files_properties(${MACOSX_ICON} PROPERTIES MACOSX_PACKAGE_LOCATION Resources)
    add_executable(citra-qt MACOSX_BUNDLE ${SRCS} ${HEADERS} ${UI_HDRS} ${ICONS} ${THEMES} ${MACOSX_ICON})
    set_target_properties(citra-qt PROPERTIES MACOSX_BUNDLE_INFO_PLIST ${CMAKE_CURRENT_SOURCE_DIR}/Info.plist)
else()
    add_executable(citra-qt ${SRCS} ${HEADERS} ${UI_HDRS} ${ICONS} ${THEMES})
endif()
target_link_libraries(citra-qt PRIVATE common core input_common network SDL2 SoundTouch xbyak)
target_link_libraries(citra-qt PRIVATE Boost::boost glad nihstro-headers Qt5::OpenGL Qt5::Widgets)
target_link_libraries(citra-qt PRIVATE ${PLATFORM_LIBRARIES} Threads::Threads)

if(SDL2_FOUND)
    target_compile_definitions(citra-qt PRIVATE HAVE_SDL2)
endif()

if(UNIX AND NOT APPLE)
    install(TARGETS citra-qt RUNTIME DESTINATION "${CMAKE_INSTALL_PREFIX}/bin")
endif()

if (MSVC)
    include(CopyCitraQt5Deps)
    include(CopyCitraSDLDeps)
    copy_citra_Qt5_deps(citra-qt)
    copy_citra_SDL_deps(citra-qt)
endif()
