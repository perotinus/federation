load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "parser.go",
        "parser_unix.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "parser_windows.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/mailru/easyjson/parser",
    visibility = ["//visibility:public"],
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
