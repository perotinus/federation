load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["thatswhyyoualwaysleaveanote.go"],
    importpath = "github.com/spf13/jwalterweatherman",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = ["jww_test.go"],
    importpath = "github.com/spf13/jwalterweatherman",
    library = ":go_default_library",
    deps = ["//vendor/github.com/stretchr/testify/assert:go_default_library"],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
