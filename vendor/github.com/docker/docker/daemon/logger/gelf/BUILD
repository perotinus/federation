load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "gelf_unsupported.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "gelf.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/docker/docker/daemon/logger/gelf",
    visibility = ["//visibility:public"],
    deps = select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/github.com/Graylog2/go-gelf/gelf:go_default_library",
            "//vendor/github.com/docker/docker/daemon/logger:go_default_library",
            "//vendor/github.com/docker/docker/daemon/logger/loggerutils:go_default_library",
            "//vendor/github.com/docker/docker/pkg/urlutil:go_default_library",
            "//vendor/github.com/sirupsen/logrus:go_default_library",
        ],
        "//conditions:default": [],
    }),
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
