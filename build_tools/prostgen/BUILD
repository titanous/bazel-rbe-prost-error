# Code Generation for protobuf using the prost library

load("@rules_rust//rust:defs.bzl", "rust_binary", "rust_doc", "rust_library", "rust_test")
load(":prostgen.bzl", "prostgen_toolchain")

package(default_visibility = ["//visibility:private"])

exports_files(["prostgen.bzl"])

rust_library(
    name = "prostgen_lib",
    srcs = [
        "extern_path.rs",
        "lib.rs",
        "module.rs",
    ],
    edition = "2018",
    deps = [
        "//third_party/cargo:anyhow",
        "//third_party/cargo:heck",
        "//third_party/cargo:prost",
        "//third_party/cargo:prost_build",
        "//third_party/cargo:prost_types",
        "//third_party/cargo:structopt",
        "//third_party/cargo:thiserror",
        "//third_party/cargo:tonic_build",
    ],
)

rust_binary(
    name = "prostgen",
    srcs = ["main.rs"],
    edition = "2018",
    visibility = ["//visibility:public"],
    deps = [
        ":prostgen_lib",
        "//third_party/cargo:anyhow",
        "//third_party/cargo:structopt",
    ],
)

prostgen_toolchain(
    name = "prostgen_toolchain_impl",
    prostgen = ":prostgen",
)

toolchain_type(
    name = "toolchain",
    visibility = ["//visibility:public"],
)

toolchain(
    name = "prostgen_toolchain",
    exec_compatible_with = [
        "@platforms//cpu:x86_64",
    ],
    target_compatible_with = [
        "@platforms//cpu:x86_64",
    ],
    toolchain = ":prostgen_toolchain_impl",
    toolchain_type = ":toolchain",
    visibility = ["//visibility:public"],
)

rust_test(
    name = "prostgen_test",
    crate = ":prostgen_lib",
)
