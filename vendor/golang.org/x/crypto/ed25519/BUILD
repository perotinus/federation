load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["ed25519.go"],
    importpath = "golang.org/x/crypto/ed25519",
    visibility = ["//visibility:public"],
    deps = ["//vendor/golang.org/x/crypto/ed25519/internal/edwards25519:go_default_library"],
)

go_test(
    name = "go_default_test",
    srcs = ["ed25519_test.go"],
    data = glob(["testdata/**"]),
    importpath = "golang.org/x/crypto/ed25519",
    library = ":go_default_library",
    deps = ["//vendor/golang.org/x/crypto/ed25519/internal/edwards25519:go_default_library"],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//vendor/golang.org/x/crypto/ed25519/internal/edwards25519:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
