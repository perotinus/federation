load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["graph.go"],
    importpath = "golang.org/x/tools/refactor/importgraph",
    visibility = ["//visibility:public"],
    deps = ["//vendor/golang.org/x/tools/go/buildutil:go_default_library"],
)

go_test(
    name = "go_default_xtest",
    srcs = ["graph_test.go"],
    importpath = "golang.org/x/tools/refactor/importgraph_test",
    deps = [":go_default_library"],
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
