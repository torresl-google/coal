# Coal, a library for collision and distance queries.

load("@rules_cc//cc:defs.bzl", "cc_library")

coal_srcs = glob(
    [
        "src/**/*.cpp",
        "src/**/*.h",
    ],
    exclude = [
        "src/serialization/*",
    ],
)

coal_hdrs = glob(
    [
        "include/coal/**/*.h",
        "include/coal/**/*.hh",
        "include/coal/**/*.hxx",
        "src/**/*.h",
    ],
    exclude = [
        "include/coal/serialization/**/*",
        "include/coal/math/vec_3f.h",
        "include/coal/math/matrix_3f.h",
        "include/coal/math/types.h",
        "include/coal/broadphase/broadphase_continuous_collision_manager.h",
        "include/coal/broadphase/broadphase_continuous_collision_manager-inl.h",
        "include/coal/internal/traversal_node_bvh_hfield.h",
    ],
)

cc_library(
    name = "coal",
    srcs = coal_srcs,
    hdrs = coal_hdrs,
    copts = [
        "-fexceptions",
    ],
    defines = [
        "COAL_HAS_OCTOMAP",
        "COAL_HAVE_OCTOMAP",
    ],
    includes = [
        "./include",
    ],
    visibility = ["//visibility:public"],
    deps = [
        "@abseil-cpp//absl/log:check",
        "@assimp",
        "@boost.filesystem",
        "@boost.math",
        "@com_gitlab_libeigen_eigen//:eigen",
        "@octomap",
    ],
)
