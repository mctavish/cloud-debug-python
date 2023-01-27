load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository", "new_git_repository")

http_archive(
    name = "bazel_skylib",
    sha256 = "74d544d96f4a5bb630d465ca8bbcfe231e3594e5aae57e1edbf17a6eb3ca2506",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/releases/download/1.3.0/bazel-skylib-1.3.0.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/releases/download/1.3.0/bazel-skylib-1.3.0.tar.gz",
    ],
)
load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")
bazel_skylib_workspace()

http_archive(
  name = "com_google_absl",
  urls = ["https://github.com/abseil/abseil-cpp/archive/98eb410c93ad059f9bba1bf43f5bb916fc92a5ea.zip"],
  strip_prefix = "abseil-cpp-98eb410c93ad059f9bba1bf43f5bb916fc92a5ea",
)

http_archive(
    name = "com_github_gflags_gflags",
    sha256 = "34af2f15cf7367513b352bdcd2493ab14ce43692d2dcd9dfc499492966c64dcf",
    strip_prefix = "gflags-2.2.2",
    urls = ["https://github.com/gflags/gflags/archive/v2.2.2.tar.gz"],
)

http_archive(
    name = "com_github_google_glog",
    sha256 = "21bc744fb7f2fa701ee8db339ded7dce4f975d0d55837a97be7d46e8382dea5a",
    strip_prefix = "glog-0.5.0",
    urls = ["https://github.com/google/glog/archive/v0.5.0.zip"],
)

http_archive(
    name = "com_google_benchmark",
    strip_prefix = "benchmark-1.7.1",
    urls = [
        "https://github.com/google/benchmark/archive/v1.7.1.tar.gz",
    ],
)

http_archive(
  name = "com_google_re2",
  urls = ["https://github.com/google/re2/archive/7272283b3842bd1d24d25ce0a6e40b63caec3fe6.zip"],
  strip_prefix = "re2-7272283b3842bd1d24d25ce0a6e40b63caec3fe6",
)

# Pinning to 1.12.1, the last release that supports C++11
http_archive(
  name = "com_google_googletest",
  urls = ["https://github.com/google/googletest/archive/58d77fa8070e8cec2dc1ed015d66b454c8d78850.tar.gz"],
  strip_prefix = "googletest-58d77fa8070e8cec2dc1ed015d66b454c8d78850",
)

# Filesystem
FILESYSTEM_BUILD = """
cc_library(
  name = "filesystem",
  hdrs = glob(["include/ghc/*"]),
  visibility = ["//visibility:public"],
)
"""

new_git_repository(
    name = "gulrak_filesystem",
    remote = "https://github.com/gulrak/filesystem.git",
    tag = "v1.3.6",
    build_file_content = FILESYSTEM_BUILD
)

# Used to build against Python.h
http_archive(
  name = "pybind11_bazel",
  strip_prefix = "pybind11_bazel-faf56fb3df11287f26dbc66fdedf60a2fc2c6631",
  urls = ["https://github.com/pybind/pybind11_bazel/archive/faf56fb3df11287f26dbc66fdedf60a2fc2c6631.zip"],
)

http_archive(
  name = "pybind11",
  build_file = "@pybind11_bazel//:pybind11.BUILD",
  strip_prefix = "pybind11-2.9.2",
  urls = ["https://github.com/pybind/pybind11/archive/v2.9.2.tar.gz"],
)
load("@pybind11_bazel//:python_configure.bzl", "python_configure")
python_configure(name = "local_config_python")#, python_interpreter_target = interpreter)

