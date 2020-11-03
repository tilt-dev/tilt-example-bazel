# Bazel BUILD file

load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")
load("@io_bazel_rules_docker//go:image.bzl", "go_image")
load("@bazel_gazelle//:def.bzl", "gazelle")

package(default_visibility = ["//visibility:public"])

# gazelle:prefix github.com/tilt-dev/tilt-example-bazel
gazelle(name = "gazelle")

web_sources = glob(["web/**"])

go_binary(
    name = "example-go",
    data = web_sources,
    embed = [":go_default_library"],
    importpath = "github.com/tilt-dev/tilt-example-bazel",
)

go_image(
    name = "example-go-image",
    # For live_update to work well, we need to use a base image with 'tar' and 'sh' in it.
    # (Bazel's default images are distroless with none of the standard unix tooling).
    # This base image is declared in WORKSPACE.
    base = "@go_base_image//image",
    data = web_sources,
    embed = [":go_default_library"],
    importpath = "github.com/tilt-dev/tilt-example-bazel",
)

go_library(
    name = "go_default_library",
    srcs = ["main.go", "start.go"],
    importpath = "github.com/tilt-dev/tilt-example-bazel",
    deps = ["@com_github_gorilla_mux//:go_default_library"],
)
