load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["doc.go"],
    importpath = "github.com/opencontainers/runc/libcontainer/integration",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "checkpoint_test.go",
        "exec_test.go",
        "execin_test.go",
        "init_test.go",
        "template_test.go",
        "utils_test.go",
    ],
    importpath = "github.com/opencontainers/runc/libcontainer/integration",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/opencontainers/runc/libcontainer:go_default_library",
        "//vendor/github.com/opencontainers/runc/libcontainer/cgroups/systemd:go_default_library",
        "//vendor/github.com/opencontainers/runc/libcontainer/configs:go_default_library",
        "//vendor/github.com/opencontainers/runc/libcontainer/nsenter:go_default_library",
        "//vendor/github.com/opencontainers/runc/libcontainer/utils:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
        "//vendor/golang.org/x/sys/unix:go_default_library",
    ],
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
