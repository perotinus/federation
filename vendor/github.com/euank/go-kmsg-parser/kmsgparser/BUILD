load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "kmsgparser.go",
        "log.go",
    ],
    importpath = "github.com/euank/go-kmsg-parser/kmsgparser",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = ["kmsgparser_test.go"],
    importpath = "github.com/euank/go-kmsg-parser/kmsgparser",
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
