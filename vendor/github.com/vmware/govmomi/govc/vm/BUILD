load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "change.go",
        "clone.go",
        "create.go",
        "destroy.go",
        "info.go",
        "ip.go",
        "markastemplate.go",
        "markasvm.go",
        "migrate.go",
        "power.go",
        "question.go",
        "register.go",
        "unregister.go",
        "vnc.go",
    ],
    importpath = "github.com/vmware/govmomi/govc/vm",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/vmware/govmomi/find:go_default_library",
        "//vendor/github.com/vmware/govmomi/govc/cli:go_default_library",
        "//vendor/github.com/vmware/govmomi/govc/flags:go_default_library",
        "//vendor/github.com/vmware/govmomi/govc/host/esxcli:go_default_library",
        "//vendor/github.com/vmware/govmomi/object:go_default_library",
        "//vendor/github.com/vmware/govmomi/property:go_default_library",
        "//vendor/github.com/vmware/govmomi/units:go_default_library",
        "//vendor/github.com/vmware/govmomi/vim25:go_default_library",
        "//vendor/github.com/vmware/govmomi/vim25/mo:go_default_library",
        "//vendor/github.com/vmware/govmomi/vim25/soap:go_default_library",
        "//vendor/github.com/vmware/govmomi/vim25/types:go_default_library",
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
    srcs = [
        ":package-srcs",
        "//vendor/github.com/vmware/govmomi/govc/vm/disk:all-srcs",
        "//vendor/github.com/vmware/govmomi/govc/vm/guest:all-srcs",
        "//vendor/github.com/vmware/govmomi/govc/vm/network:all-srcs",
        "//vendor/github.com/vmware/govmomi/govc/vm/rdm:all-srcs",
        "//vendor/github.com/vmware/govmomi/govc/vm/snapshot:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
