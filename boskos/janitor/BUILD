package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_binary",
    "go_library",
    "go_test",
)

go_binary(
    name = "janitor",
    importpath = "k8s.io/test-infra/boskos/janitor",
    library = ":go_default_library",
)

go_library(
    name = "go_default_library",
    srcs = ["janitor.go"],
    importpath = "k8s.io/test-infra/boskos/janitor",
    deps = [
        "//boskos/client:go_default_library",
        "//boskos/common:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
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
)

go_test(
    name = "go_default_test",
    srcs = ["janitor_test.go"],
    importpath = "k8s.io/test-infra/boskos/janitor",
    library = ":go_default_library",
    deps = ["//boskos/common:go_default_library"],
)
