set(SRCS
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
            )

set(HEADERS
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
            )

if(ARCHITECTURE_x86_64)
    set(SRCS ${SRCS}
            ../video_core/shader/shader_jit_x64.cpp
            ../video_core/shader/shader_jit_x64_compiler.cpp)

    set(HEADERS ${HEADERS}
            ../video_core/shader/shader_jit_x64.h
            ../video_core/shader/shader_jit_x64_compiler.h)
endif()

create_directory_groups(${SRCS} ${HEADERS})

add_library(video_core STATIC ${SRCS} ${HEADERS})
target_link_libraries(video_core PUBLIC common core)
target_link_libraries(video_core PRIVATE glad nihstro-headers)

if (ARCHITECTURE_x86_64)
    target_link_libraries(video_core PRIVATE xbyak)
endif()

if (PNG_FOUND)
    target_link_libraries(video_core PRIVATE PNG::PNG)
    target_compile_definitions(video_core PRIVATE HAVE_PNG)
endif()
