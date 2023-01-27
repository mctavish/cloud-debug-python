package(default_visibility = ["//visibility:public"])

cc_library(
    name = "test_main",
    testonly = 1,
    srcs = ["test_main.cc"],
    deps = [
        "//src/googleclouddebugger:common",
        "@com_github_google_glog//:glog",
        "@com_google_googletest//:gtest",
        "@com_google_benchmark//:benchmark",
        "@local_config_python//:python_headers",
        "@local_config_python//:python_embed",
        "@com_github_gflags_gflags//:gflags",
    ],
)

cc_library(
    name = "native_test_util",
    testonly = 1,
    srcs = ["native_test_util.cc"],
    hdrs = ["native_test_util.h"],
    deps = [
        "//src/googleclouddebugger:common",
	"//src/googleclouddebugger:python_util",
        "@com_google_googletest//:gtest",
	"@com_google_re2//:re2",
	"@com_google_absl//absl/strings",
	"@gulrak_filesystem//:filesystem",
    ],
)

cc_test(
    name = "bytecode_breakpoint_test",
    srcs = ["bytecode_breakpoint_test.cc"],
    deps = [
        ":native_test_util",
        "//src/googleclouddebugger:bytecode_breakpoint",
        "@com_google_benchmark//:benchmark",
        "@com_google_googletest//:gtest_main",
    ],
)

cc_test(
    name = "bytecode_manipulator_test",
    srcs = ["bytecode_manipulator_test.cc"],
    deps = [
        "//src/googleclouddebugger:bytecode_manipulator",
        "@com_google_googletest//:gtest_main",
    ],
)
