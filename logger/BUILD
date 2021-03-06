load("@rules_cc//cc:defs.bzl", "cc_library", "cc_test")
load("//build:cpplint.bzl", "cpplint")
load("//build/install:install.bzl", "install", "install_files")

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "logger",
    srcs = ["logger.cc"],
    hdrs = ["logger.h"],
    deps = [
        "//common",
        "//logger:log_file_object",
    ],
)

cc_test(
    name = "logger_test",
    size = "small",
    srcs = ["logger_test.cc"],
    deps = [
        "//:cyber",
        "@com_google_googletest//:gtest_main",
    ],
)

cc_library(
    name = "async_logger",
    srcs = ["async_logger.cc"],
    hdrs = ["async_logger.h"],
    deps = [
        "//base:macros",
        "//common",
        "//logger:log_file_object",
    ],
)

cc_test(
    name = "async_logger_test",
    size = "small",
    srcs = ["async_logger_test.cc"],
    deps = [
        "//:cyber",
        "@com_google_googletest//:gtest_main",
    ],
)

cc_library(
    name = "log_file_object",
    srcs = ["log_file_object.cc"],
    hdrs = ["log_file_object.h"],
    deps = [
        "//:binary",
        "//common:log",
        "//logger:logger_util",
    ],
)

cc_test(
    name = "log_file_object_test",
    size = "small",
    srcs = ["log_file_object_test.cc"],
    deps = [
        "//:cyber",
        "@com_google_googletest//:gtest_main",
    ],
)

cc_library(
    name = "logger_util",
    srcs = ["logger_util.cc"],
    hdrs = ["logger_util.h"],
    deps = [
        "//common:global_data",
    ],
)

cc_test(
    name = "logger_util_test",
    size = "small",
    srcs = ["logger_util_test.cc"],
    deps = [
        "//:cyber",
        "@com_google_googletest//:gtest_main",
    ],
)

cpplint()

install(
    name = "install",
    deps = [
        ":logger_lib",
    ],
)

install_files(
    name = "logger_lib",
    dest = "lib/logger",
    files = [
        ":async_logger",
        ":log_file_object",
        ":logger_util",
    ],
)
