load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "doc.go",
        "error.go",
        "oauth2.go",
    ],
    importpath = "github.com/coreos/go-oidc/oauth2",
    visibility = ["//visibility:public"],
    deps = ["//vendor/github.com/coreos/go-oidc/http:go_default_library"],
)

go_test(
    name = "go_default_test",
    srcs = ["oauth2_test.go"],
    importpath = "github.com/coreos/go-oidc/oauth2",
    library = ":go_default_library",
    deps = ["//vendor/github.com/coreos/go-oidc/http:go_default_library"],
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
