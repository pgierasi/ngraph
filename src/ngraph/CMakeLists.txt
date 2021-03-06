# ******************************************************************************
# Copyright 2017-2019 Intel Corporation
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
# ******************************************************************************

set (SRC
    assertion.hpp
    autodiff/adjoints.cpp
    autodiff/adjoints.hpp
    axis_set.cpp
    axis_set.hpp
    axis_vector.cpp
    axis_vector.hpp
    builder/autobroadcast.cpp
    builder/autobroadcast.hpp
    builder/make_constant.hpp
    builder/numpy_transpose.cpp
    builder/numpy_transpose.hpp
    builder/quantization.cpp
    builder/quantization.hpp
    builder/quantization/quantized_linear_convolution.cpp
    builder/quantization/quantized_linear_convolution.hpp
    builder/quantization_util.hpp
    builder/reduce_ops.cpp
    builder/reduce_ops.hpp
    builder/tensor_mask.hpp
    check.hpp
    code_writer.hpp
    coordinate.cpp
    coordinate.hpp
    coordinate_diff.cpp
    coordinate_diff.hpp
    coordinate_transform.cpp
    cpio.cpp
    cpio.hpp
    descriptor/input.cpp
    descriptor/input.hpp
    descriptor/layout/dense_tensor_layout.cpp
    descriptor/layout/dense_tensor_layout.hpp
    descriptor/layout/tensor_layout.cpp
    descriptor/layout/tensor_layout.hpp
    descriptor/output.cpp
    descriptor/output.hpp
    descriptor/tensor.cpp
    descriptor/tensor.hpp
    dimension.cpp
    dimension.hpp
    except.hpp
    file_util.cpp
    file_util.hpp
    function.cpp
    function.hpp
    graph_util.cpp
    log.cpp
    log.hpp
    ngraph.cpp
    ngraph.hpp
    ngraph_visibility.hpp
    node.cpp
    node.hpp
    node_vector.hpp
    op/abs.cpp
    op/abs.hpp
    op/acos.cpp
    op/acos.hpp
    op/add.cpp
    op/add.hpp
    op/all.cpp
    op/all.hpp
    op/allreduce.cpp
    op/allreduce.hpp
    op/and.cpp
    op/and.hpp
    op/any.cpp
    op/any.hpp
    op/argmax.cpp
    op/argmax.hpp
    op/argmin.cpp
    op/argmin.hpp
    op/asin.cpp
    op/asin.hpp
    op/atan.cpp
    op/atan.hpp
    op/avg_pool.cpp
    op/avg_pool.hpp
    op/batch_norm.cpp
    op/batch_norm.hpp
    op/broadcast.cpp
    op/broadcast.hpp
    op/ceiling.cpp
    op/ceiling.hpp
    op/concat.cpp
    op/concat.hpp
    op/constant.cpp
    op/constant.hpp
    op/convert.cpp
    op/convert.hpp
    op/convolution.cpp
    op/convolution.hpp
    op/cos.cpp
    op/cos.hpp
    op/cosh.cpp
    op/cosh.hpp
    op/dequantize.cpp
    op/dequantize.hpp
    op/divide.cpp
    op/divide.hpp
    op/dot.cpp
    op/dot.hpp
    op/embedding_lookup.cpp
    op/embedding_lookup.hpp
    op/equal.cpp
    op/equal.hpp
    op/exp.cpp
    op/exp.hpp
    op/experimental/generate_mask.cpp
    op/experimental/generate_mask.hpp
    op/experimental/quantized_avg_pool.cpp
    op/experimental/quantized_avg_pool.hpp
    op/experimental/quantized_concat.cpp
    op/experimental/quantized_concat.hpp
    op/experimental/quantized_conv.cpp
    op/experimental/quantized_conv.hpp
    op/experimental/quantized_conv_bias.cpp
    op/experimental/quantized_conv_bias.hpp
    op/experimental/quantized_conv_relu.cpp
    op/experimental/quantized_conv_relu.hpp
    op/experimental/quantized_max_pool.cpp
    op/experimental/quantized_max_pool.hpp
    op/experimental/shape_of.cpp
    op/experimental/shape_of.hpp
    op/floor.cpp
    op/floor.hpp
    op/get_output_element.cpp
    op/get_output_element.hpp
    op/greater.cpp
    op/greater.hpp
    op/greater_eq.cpp
    op/greater_eq.hpp
    op/less.cpp
    op/less.hpp
    op/less_eq.cpp
    op/less_eq.hpp
    op/log.cpp
    op/log.hpp
    op/lrn.cpp
    op/lrn.hpp
    op/max.cpp
    op/max.hpp
    op/max_pool.cpp
    op/max_pool.hpp
    op/maximum.cpp
    op/maximum.hpp
    op/min.cpp
    op/min.hpp
    op/minimum.cpp
    op/minimum.hpp
    op/multiply.cpp
    op/multiply.hpp
    op/negative.cpp
    op/negative.hpp
    op/not.cpp
    op/not.hpp
    op/not_equal.cpp
    op/not_equal.hpp
    op/one_hot.cpp
    op/one_hot.hpp
    op/op.cpp
    op/op.hpp
    op/or.cpp
    op/or.hpp
    op/pad.cpp
    op/pad.hpp
    op/parameter.cpp
    op/parameter.hpp
    op/passthrough.cpp
    op/passthrough.hpp
    op/power.cpp
    op/power.hpp
    op/product.cpp
    op/product.hpp
    op/quantize.cpp
    op/quantize.hpp
    op/relu.cpp
    op/relu.hpp
    op/replace_slice.cpp
    op/replace_slice.hpp
    op/reshape.cpp
    op/reshape.hpp
    op/result.cpp
    op/result.hpp
    op/reverse.cpp
    op/reverse.hpp
    op/reverse_sequence.cpp
    op/reverse_sequence.hpp
    op/select.cpp
    op/select.hpp
    op/sigmoid.cpp
    op/sigmoid.hpp
    op/sign.cpp
    op/sign.hpp
    op/sin.cpp
    op/sin.hpp
    op/sinh.cpp
    op/sinh.hpp
    op/slice.cpp
    op/slice.hpp
    op/softmax.cpp
    op/softmax.hpp
    op/sqrt.cpp
    op/sqrt.hpp
    op/stop_gradient.cpp
    op/stop_gradient.hpp
    op/subtract.cpp
    op/subtract.hpp
    op/sum.cpp
    op/sum.hpp
    op/tan.cpp
    op/tan.hpp
    op/tanh.cpp
    op/tanh.hpp
    op/topk.cpp
    op/topk.hpp
    op/util/arithmetic_reduction.cpp
    op/util/arithmetic_reduction.hpp
    op/util/binary_elementwise_arithmetic.cpp
    op/util/binary_elementwise_arithmetic.hpp
    op/util/binary_elementwise_comparison.cpp
    op/util/binary_elementwise_comparison.hpp
    op/util/binary_elementwise_logical.cpp
    op/util/binary_elementwise_logical.hpp
    op/util/index_reduction.cpp
    op/util/index_reduction.hpp
    op/util/logical_reduction.cpp
    op/util/logical_reduction.hpp
    op/util/unary_elementwise_arithmetic.cpp
    op/util/unary_elementwise_arithmetic.hpp
    parameter_vector.hpp
    partial_shape.cpp
    partial_shape.hpp
    pass/algebraic_simplification.cpp
    pass/algebraic_simplification.hpp
    pass/assign_layout.hpp
    pass/common_function_collection.cpp
    pass/common_function_collection.hpp
    pass/constant_folding.cpp
    pass/constant_folding.hpp
    pass/core_fusion.cpp
    pass/core_fusion.hpp
    pass/cse.cpp
    pass/cse.hpp
    pass/dump_sorted.cpp
    pass/dump_sorted.hpp
    pass/get_output_element_elimination.cpp
    pass/get_output_element_elimination.hpp
    pass/graph_rewrite.cpp
    pass/graph_rewrite.hpp
    pass/like_replacement.cpp
    pass/like_replacement.hpp
    pass/liveness.cpp
    pass/liveness.hpp
    pass/manager.cpp
    pass/manager.hpp
    pass/manager_state.cpp
    pass/manager_state.hpp
    pass/memory_layout.cpp
    pass/memory_layout.hpp
    pass/memory_visualize.cpp
    pass/memory_visualize.hpp
    pass/nop_elimination.cpp
    pass/nop_elimination.hpp
    pass/pass.cpp
    pass/pass.hpp
    pass/pass_config.cpp
    pass/pass_config.hpp
    pass/prefix_reshape_elimination.cpp
    pass/prefix_reshape_elimination.hpp
    pass/propagate_cacheability.cpp
    pass/propagate_cacheability.hpp
    pass/reshape_elimination.cpp
    pass/reshape_elimination.hpp
    pass/reshape_sinking.cpp
    pass/reshape_sinking.hpp
    pass/serialize.cpp
    pass/serialize.hpp
    pass/validate_graph.cpp
    pass/validate_graph.hpp
    pass/visualize_tree.cpp
    pass/visualize_tree.hpp
    pass/zero_dim_tensor_elimination.cpp
    pass/zero_dim_tensor_elimination.cpp
    pass/zero_dim_tensor_elimination.hpp
    pass/zero_dim_tensor_elimination.hpp
    pattern/matcher.cpp
    pattern/matcher.hpp
    pattern/op/any.hpp
    pattern/op/any_of.hpp
    pattern/op/label.hpp
    pattern/op/pattern.hpp
    pattern/op/skip.hpp
    placement.cpp
    placement.hpp
    rank.hpp
    result_vector.hpp
    runtime/aligned_buffer.cpp
    runtime/aligned_buffer.hpp
    runtime/backend.cpp
    runtime/backend.hpp
    runtime/backend_manager.cpp
    runtime/backend_manager.hpp
    runtime/executable.cpp
    runtime/executable.hpp
    runtime/host_tensor.cpp
    runtime/host_tensor.hpp
    runtime/performance_counter.hpp
    runtime/tensor.cpp
    runtime/tensor.hpp
    serializer.cpp
    serializer.hpp
    shape.cpp
    shape.hpp
    shape_util.cpp
    shape_util.hpp
    state/rng_state.cpp
    strides.cpp
    strides.hpp
    type/bfloat16.cpp
    type/element_type.cpp
    util.cpp
    util.hpp
    validation_util.cpp
    validation_util.hpp
    )

set(SRC ${SRC}
    runtime/hybrid/hybrid_backend.cpp
    runtime/hybrid/hybrid_backend.hpp
    runtime/hybrid/hybrid_executable.cpp
    runtime/hybrid/hybrid_executable.hpp
    runtime/hybrid/hybrid_util.cpp
    runtime/hybrid/hybrid_util.hpp
    runtime/hybrid/op/function_call.cpp
    runtime/hybrid/op/function_call.hpp
    runtime/hybrid/pass/default_placement.cpp
    runtime/hybrid/pass/default_placement.hpp
    runtime/hybrid/pass/dump.cpp
    runtime/hybrid/pass/dump.hpp
    runtime/hybrid/pass/fix_get_output_element.cpp
    runtime/hybrid/pass/fix_get_output_element.hpp
    runtime/hybrid/pass/liveness.cpp
    runtime/hybrid/pass/liveness.hpp
    runtime/hybrid/pass/memory_layout.cpp
    runtime/hybrid/pass/memory_layout.hpp
    )


if(NGRAPH_DISTRIBUTED_ENABLE)
    list(APPEND SRC distributed.cpp distributed.hpp)
endif()

configure_file(version.in.hpp version.hpp)

add_library(ngraph SHARED ${SRC})

if(NGRAPH_DISTRIBUTED_ENABLE)
    target_sources(ngraph PRIVATE distributed.cpp)
    if(NGRAPH_DISTRIBUTED_MLSL_ENABLE)
        target_include_directories(ngraph SYSTEM PRIVATE libmlsl)
        target_link_libraries(ngraph PRIVATE libmlsl)
    elseif(NGRAPH_DISTRIBUTED_OMPI_ENABLE)
        find_package(MPI REQUIRED)
        target_include_directories(ngraph SYSTEM PRIVATE ${MPI_C_INCLUDE_PATH} ${MPI_CXX_INCLUDE_PATH})
        target_link_libraries(ngraph PRIVATE ${MPI_C_LIBRARIES} ${MPI_CXX_LIBRARIES})
    else()
        message(FATAL_ERROR "Distributed Library not supported/mentioned")
    endif()
endif()

add_subdirectory(frontend)

find_package(Graphviz QUIET)
if (GRAPHVIZ_FOUND)
    set_property(SOURCE pass/visualize_tree.cpp APPEND PROPERTY COMPILE_DEFINITIONS GRAPHVIZ_FOUND)
endif()

if(NGRAPH_ADDRESS_SANITIZER)
    message(STATUS "Enable Address Sanitizer")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -fsanitize=address -fno-omit-frame-pointer")
endif()

add_subdirectory(codegen)
add_subdirectory(runtime)

target_compile_definitions(ngraph
    PRIVATE
        SHARED_LIB_PREFIX="${CMAKE_SHARED_LIBRARY_PREFIX}"
        SHARED_LIB_SUFFIX="${CMAKE_SHARED_LIBRARY_SUFFIX}"
        NGRAPH_DLL_EXPORTS
)
if(NGRAPH_LIB_VERSIONING_ENABLE)
    set_target_properties(ngraph PROPERTIES
        VERSION ${NGRAPH_VERSION}
        SOVERSION ${NGRAPH_API_VERSION})
endif()
target_link_libraries(ngraph PRIVATE libjson)
target_compile_definitions(ngraph PUBLIC NGRAPH_VERSION="${NGRAPH_VERSION}")

if (LINUX)
    set_property(TARGET ngraph APPEND_STRING PROPERTY LINK_FLAGS " -Wl,--rpath,$ORIGIN")

    # nGraph links against one or more libraries (ex. LLVM) but we don't want to
    # export these symbols as part of the DSO. This is a GNU ld (and derivatives) specific
    # option so making this portable is still an open issue. As a note for the future,
    # this is not an issue on Windows and LLVM's lld does support --exclude-libs.
    set_property(TARGET ngraph APPEND_STRING PROPERTY LINK_FLAGS " -Wl,--exclude-libs,ALL")

    # GCC invokes the linker with --as-needed by default which doesn't work for us
    # because generated code needs to find symbols in these DSOs at runtime.
    # The fix below is temporary and will be removed once we find a better way
    # to do this because certain dependencies like the OpenMP runtime libraries
    # _do_ need to be linked with --as-needed with a higher priority for the
    # Intel OpenMP runtime so we don't mix libgomp and libiomp5
    if (CMAKE_CXX_COMPILER_ID STREQUAL "GNU")
        set_property(TARGET ngraph APPEND_STRING PROPERTY LINK_FLAGS " -Wl,--no-as-needed")
    endif()
elseif(APPLE)
    set_property(TARGET ngraph APPEND_STRING PROPERTY LINK_FLAGS " -Wl,-rpath,@loader_path")
endif()

# Defines macro in C++ to load backend plugin
target_include_directories(ngraph PUBLIC "${NGRAPH_INCLUDE_PATH}")
if (NOT WIN32)
    target_link_libraries(ngraph PUBLIC dl pthread)
endif()

if (NGRAPH_ONNX_IMPORT_ENABLE)
    target_sources(ngraph PRIVATE $<TARGET_OBJECTS:onnx_import_interface>)
    target_link_libraries(ngraph PRIVATE onnx_import)
endif()

# Build subdirectories for all build types on Windows
if(WIN32)
    foreach(BUILD_TYPE Release Debug RelWithDebInfo MinSizeRel)
        if(NOT EXISTS ${NGRAPH_BUILD_DIR}/${BUILD_TYPE})
            file(MAKE_DIRECTORY ${NGRAPH_BUILD_DIR}/${BUILD_TYPE})
        endif()
    endforeach()
endif()

#-----------------------------------------------------------------------------------------------
# Installation logic...
#-----------------------------------------------------------------------------------------------

# nGraph
install(FILES ${CMAKE_BINARY_DIR}/VERSION DESTINATION ${CMAKE_INSTALL_PREFIX})
install(TARGETS ngraph DESTINATION ${NGRAPH_INSTALL_LIB})  # libngraph.so
install(DIRECTORY
    ${CMAKE_CURRENT_SOURCE_DIR}/
    DESTINATION "${NGRAPH_INSTALL_INCLUDE}/ngraph"
    FILES_MATCHING
        PATTERN "*.hpp"
        PATTERN "*.h"
)
install(FILES ${CMAKE_BINARY_DIR}/src/ngraph/version.hpp
    DESTINATION "${NGRAPH_INSTALL_INCLUDE}/ngraph")

set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_PACKAGE_SHLIBDEPS ON)
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "A most excellent graph library")
set(CPACK_PACKAGE_NAME "nGraph")
set(CPACK_PACKAGE_CONTACT "Robert Kimball")
# set(CPACK_PACKAGE_VERSION
set(CPACK_PACKAGE_VENDOR "Intel Nervana")
# set(CPACK_PACKAGE_DESCRIPTION_FILE "")

set(CPACK_PACKAGE_VERSION_MAJOR ${NGRAPH_VERSION_MAJOR})
set(CPACK_PACKAGE_VERSION_MINOR ${NGRAPH_VERSION_MINOR})
set(CPACK_PACKAGE_VERSION_PATCH ${NGRAPH_VERSION_PATCH})
include(CPack)
