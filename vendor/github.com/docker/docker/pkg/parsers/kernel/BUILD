load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "kernel.go",
        "uname_unsupported.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:darwin_amd64": [
            "kernel_darwin.go",
        ],
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "kernel_unix.go",
            "uname_linux.go",
        ],
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "kernel_windows.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/docker/docker/pkg/parsers/kernel",
    visibility = ["//visibility:public"],
    deps = select({
        "@io_bazel_rules_go//go/platform:darwin_amd64": [
            "//vendor/github.com/mattn/go-shellwords:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/github.com/sirupsen/logrus:go_default_library",
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "//vendor/golang.org/x/sys/windows:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_test(
    name = "go_default_test",
    srcs = ["kernel_unix_test.go"],
    importpath = "github.com/docker/docker/pkg/parsers/kernel",
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
