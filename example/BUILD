load("@gazelle//:def.bzl", "gazelle")

# gazelle:prefix e2e
# gazelle:map_kind bzl_library bzl_library @aspect_bazel_lib//:bzl_library.bzl
gazelle(
    name = "gazelle",
    gazelle = select({
        "@bazel_tools//src/conditions:linux_x86_64": "@gazelle_prebuilt_linux_amd64//file",
        "@bazel_tools//src/conditions:darwin_arm64": "@gazelle_prebuilt_darwin_arm64//file",
    }),
)
