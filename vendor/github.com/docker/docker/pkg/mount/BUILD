load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "flags.go",
        "flags_unsupported.go",
        "mount.go",
        "mounter_unsupported.go",
        "mountinfo.go",
        "mountinfo_unsupported.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "flags_linux.go",
            "mounter_linux.go",
            "mountinfo_linux.go",
            "sharedsubtree_linux.go",
        ],
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "mountinfo_windows.go",
        ],
        "//conditions:default": [],
    }),
    cgo = True,
    importpath = "github.com/docker/docker/pkg/mount",
    visibility = ["//visibility:public"],
    deps = select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_test(
    name = "go_default_test",
    srcs = [
        "mount_unix_test.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "mounter_linux_test.go",
            "mountinfo_linux_test.go",
            "sharedsubtree_linux_test.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/docker/docker/pkg/mount",
    library = ":go_default_library",
    deps = select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
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
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
