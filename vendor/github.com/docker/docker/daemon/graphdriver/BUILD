load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "counter.go",
        "driver.go",
        "driver_unsupported.go",
        "fsdiff.go",
        "plugin.go",
        "proxy.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "driver_linux.go",
        ],
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "driver_windows.go",
        ],
        "//conditions:default": [],
    }),
    cgo = True,
    importpath = "github.com/docker/docker/daemon/graphdriver",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/docker/docker/pkg/archive:go_default_library",
        "//vendor/github.com/docker/docker/pkg/chrootarchive:go_default_library",
        "//vendor/github.com/docker/docker/pkg/idtools:go_default_library",
        "//vendor/github.com/docker/docker/pkg/ioutils:go_default_library",
        "//vendor/github.com/docker/docker/pkg/plugingetter:go_default_library",
        "//vendor/github.com/docker/docker/pkg/plugins:go_default_library",
        "//vendor/github.com/docker/docker/plugin/v2:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
        "//vendor/github.com/vbatts/tar-split/tar/storage:go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/github.com/docker/docker/pkg/mount:go_default_library",
            "//vendor/golang.org/x/sys/unix:go_default_library",
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
    srcs = [
        ":package-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/aufs:all-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/btrfs:all-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/devmapper:all-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/graphtest:all-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/lcow:all-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/overlay:all-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/overlay2:all-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/overlayutils:all-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/quota:all-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/register:all-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/vfs:all-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/windows:all-srcs",
        "//vendor/github.com/docker/docker/daemon/graphdriver/zfs:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
