load("//:bzl_library.bzl", "bzl_library")

licenses(["notice"])

package(default_visibility = ["//visibility:public"])

bzl_library(
    name = "build_test",
    srcs = ["build_test.bzl"],
    deps = ["//lib:new_sets"],
)

bzl_library(
    name = "copy_file",
    srcs = ["copy_file.bzl"],
    deps = [":copy_file_private"],
)

bzl_library(
    name = "copy_file_private",
    srcs = ["copy_file_private.bzl"],
    visibility = ["//visibility:private"],
)

bzl_library(
    name = "maprule",
    srcs = ["maprule.bzl"],
    deps = [":maprule_private"],
)

bzl_library(
    name = "maprule_private",
    srcs = ["maprule_private.bzl"],
    visibility = ["//visibility:private"],
    deps = [
        ":maprule_util",
        "//lib:dicts",
        "//lib:paths",
    ],
)

bzl_library(
    name = "maprule_util",
    srcs = ["maprule_util.bzl"],
)

# Exported for build_test.bzl to make sure of, it is an implementation detail
# of the rule and should not be directly used by anything else.
exports_files(["empty_test.sh"])

filegroup(
    name = "test_deps",
    testonly = True,
    srcs = [
        "BUILD",
        "empty_test.sh",
    ] + glob(["*.bzl"]),
)
