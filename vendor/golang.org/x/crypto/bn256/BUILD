load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "bn256.go",
        "constants.go",
        "curve.go",
        "gfp12.go",
        "gfp2.go",
        "gfp6.go",
        "optate.go",
        "twist.go",
    ],
    importpath = "golang.org/x/crypto/bn256",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "bn256_test.go",
        "example_test.go",
    ],
    importpath = "golang.org/x/crypto/bn256",
    library = ":go_default_library",
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
