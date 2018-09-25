licenses(["notice"])  # 3-Clause BSD

exports_files(["LICENSE"])

cc_library(
    name = "ngraph_headers",
    hdrs = glob(["src/ngraph/**/*.hpp"]),
    visibility = ["//visibility:public"],
)

cc_library(
    name = "ngraph_cpu_backend",
    srcs = [
        "src/ngraph/runtime/cpu/builder/add.cpp",
        "src/ngraph/runtime/cpu/builder/allreduce.cpp",
        "src/ngraph/runtime/cpu/builder/argmax.cpp",
        "src/ngraph/runtime/cpu/builder/argmin.cpp",
        "src/ngraph/runtime/cpu/builder/avg_pool.cpp",
        "src/ngraph/runtime/cpu/builder/batch_norm.cpp",
        "src/ngraph/runtime/cpu/builder/bounded_relu.cpp",
        "src/ngraph/runtime/cpu/builder/broadcast.cpp",
        "src/ngraph/runtime/cpu/builder/concat.cpp",
        "src/ngraph/runtime/cpu/builder/convert.cpp",
        "src/ngraph/runtime/cpu/builder/convert_layout.cpp",
        "src/ngraph/runtime/cpu/builder/convolution.cpp",
        "src/ngraph/runtime/cpu/builder/dot.cpp",
        "src/ngraph/runtime/cpu/builder/function_call.cpp",
        "src/ngraph/runtime/cpu/builder/lrn.cpp",
        "src/ngraph/runtime/cpu/builder/lstm.cpp",
        "src/ngraph/runtime/cpu/builder/matmul_bias.cpp",
        "src/ngraph/runtime/cpu/builder/max.cpp",
        "src/ngraph/runtime/cpu/builder/max_pool.cpp",
        "src/ngraph/runtime/cpu/builder/min.cpp",
        "src/ngraph/runtime/cpu/builder/one_hot.cpp",
        "src/ngraph/runtime/cpu/builder/pad.cpp",
        "src/ngraph/runtime/cpu/builder/product.cpp",
        "src/ngraph/runtime/cpu/builder/quantize.cpp",
        "src/ngraph/runtime/cpu/builder/quantized_avg_pool.cpp",
        "src/ngraph/runtime/cpu/builder/quantized_max_pool.cpp",
        "src/ngraph/runtime/cpu/builder/reduce_function.cpp",
        "src/ngraph/runtime/cpu/builder/reduce_function_window.cpp",
        "src/ngraph/runtime/cpu/builder/relu.cpp",
        "src/ngraph/runtime/cpu/builder/replace_slice.cpp",
        "src/ngraph/runtime/cpu/builder/reshape.cpp",
        "src/ngraph/runtime/cpu/builder/reverse.cpp",
        "src/ngraph/runtime/cpu/builder/reverse_sequence.cpp",
        "src/ngraph/runtime/cpu/builder/rnn.cpp",
        "src/ngraph/runtime/cpu/builder/select.cpp",
        "src/ngraph/runtime/cpu/builder/select_and_scatter.cpp",
        "src/ngraph/runtime/cpu/builder/sigmoid.cpp",
        "src/ngraph/runtime/cpu/builder/slice.cpp",
        "src/ngraph/runtime/cpu/builder/softmax.cpp",
        "src/ngraph/runtime/cpu/builder/sum.cpp",
        "src/ngraph/runtime/cpu/builder/topk.cpp",
        "src/ngraph/runtime/cpu/cpu_backend.cpp",
        "src/ngraph/runtime/cpu/cpu_builder.cpp",
        "src/ngraph/runtime/cpu/cpu_call_frame.cpp",
        "src/ngraph/runtime/cpu/cpu_external_function.cpp",
        "src/ngraph/runtime/cpu/cpu_kernels.cpp",
        "src/ngraph/runtime/cpu/cpu_layout_descriptor.cpp",
        "src/ngraph/runtime/cpu/cpu_tensor_view.cpp",
        "src/ngraph/runtime/cpu/cpu_tensor_view_wrapper.cpp",
        "src/ngraph/runtime/cpu/cpu_tracing.cpp",
        "src/ngraph/runtime/cpu/kernel/eigen_thread_pool.cpp",
        "src/ngraph/runtime/cpu/kernel/pad.cpp",
        "src/ngraph/runtime/cpu/kernel/reduce_max.cpp",
        "src/ngraph/runtime/cpu/kernel/reduce_sum.cpp",
        "src/ngraph/runtime/cpu/kernel/reshape.cpp",
        "src/ngraph/runtime/cpu/mkldnn_emitter.cpp",
        "src/ngraph/runtime/cpu/mkldnn_invoke.cpp",
        "src/ngraph/runtime/cpu/mkldnn_utils.cpp",
        "src/ngraph/runtime/cpu/op/batch_dot.cpp",
        "src/ngraph/runtime/cpu/op/batch_norm_relu.cpp",
        "src/ngraph/runtime/cpu/op/bounded_relu.cpp",
        "src/ngraph/runtime/cpu/op/conv_add.cpp",
        "src/ngraph/runtime/cpu/op/conv_bias.cpp",
        "src/ngraph/runtime/cpu/op/conv_relu.cpp",
        "src/ngraph/runtime/cpu/op/convert_layout.cpp",
        "src/ngraph/runtime/cpu/op/dequantize.cpp",
        "src/ngraph/runtime/cpu/op/group_conv.cpp",
        "src/ngraph/runtime/cpu/op/loop_kernel.cpp",
        "src/ngraph/runtime/cpu/op/lstm.cpp",
        "src/ngraph/runtime/cpu/op/matmul_bias.cpp",
        "src/ngraph/runtime/cpu/op/max_pool_with_indices.cpp",
        "src/ngraph/runtime/cpu/op/quantize.cpp",
        "src/ngraph/runtime/cpu/op/quantized_avg_pool.cpp",
        "src/ngraph/runtime/cpu/op/quantized_max_pool.cpp",
        "src/ngraph/runtime/cpu/op/rnn.cpp",
        "src/ngraph/runtime/cpu/op/sigmoid_mul.cpp",
        "src/ngraph/runtime/cpu/pass/cpu_assignment.cpp",
        "src/ngraph/runtime/cpu/pass/cpu_collapse_dims.cpp",
        "src/ngraph/runtime/cpu/pass/cpu_concat_inputs.cpp",
        "src/ngraph/runtime/cpu/pass/cpu_fusion.cpp",
        "src/ngraph/runtime/cpu/pass/cpu_layout.cpp",
        "src/ngraph/runtime/cpu/pass/cpu_loop_kernel_fusion.cpp",
        "src/ngraph/runtime/cpu/pass/cpu_mat_fusion.cpp",
        "src/ngraph/runtime/cpu/pass/cpu_post_layout_optimizations.cpp",
        "src/ngraph/runtime/cpu/pass/cpu_rnn_fusion.cpp",
        "src/ngraph/runtime/cpu/pass/cpu_workspace_insertion.cpp",
    ],
    hdrs = glob(["src/ngraph/runtime/cpu/**/*.hpp"]) + glob([]),
    deps = [
        ":ngraph_headers",
        "@eigen_archive//:eigen",
        "@nlohmann_json_lib",
        "@tbb",
        "@mkl_dnn//:mkl_dnn",
    ],
    copts = [
        "-I external/ngraph/src",
        "-I external/nlohmann_json_lib/include/",
        '-D SHARED_LIB_EXT=\\".so\\"',
        '-D NGRAPH_VERSION=\\"0.8.0\\"',
        "-D NGRAPH_DEX_ONLY",
    ],
    visibility = ["//visibility:public"],
    alwayslink = 1,
)

cc_library(
    name = "ngraph_core",
    srcs = glob([
        "src/ngraph/*.cpp",
        "src/ngraph/autodiff/*.cpp",
        "src/ngraph/builder/*.cpp",
        "src/ngraph/descriptor/*.cpp",
        "src/ngraph/descriptor/layout/*.cpp",
        "src/ngraph/op/*.cpp",
        "src/ngraph/op/util/*.cpp",
        "src/ngraph/pattern/*.cpp",
        "src/ngraph/pattern/*.hpp",
        "src/ngraph/pass/*.cpp",
        "src/ngraph/pass/*.hpp",
        "src/ngraph/runtime/*.cpp",
        "src/ngraph/type/*.cpp",
    ]),
    deps = [
        ":ngraph_headers",
        ":ngraph_cpu_backend",
        "@eigen_archive//:eigen",
        "@nlohmann_json_lib",
    ],
    copts = [
        "-I external/ngraph/src",
        "-I external/nlohmann_json_lib/include/",
        '-D SHARED_LIB_EXT=\\".so\\"',
        '-D NGRAPH_VERSION=\\"0.8.0\\"',
    ],
    visibility = ["//visibility:public"],
    alwayslink = 1,
)
