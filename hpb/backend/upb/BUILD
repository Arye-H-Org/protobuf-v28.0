# Copyright (c) 2024, Google LLC
# All rights reserved.
#
# Use of this source code is governed by a BSD-style
# license that can be found in the LICENSE file or at
# https://developers.google.com/open-source/licenses/bsd

load(
    "//upb/bazel:build_defs.bzl",
    "UPB_DEFAULT_CPPOPTS",
)

package(default_applicable_licenses = ["//:license"])

cc_library(
    name = "upb",
    hdrs = ["upb.h"],
    visibility = ["//upb:friends"],
    deps = [
        ":interop",
        "//hpb:ptr",
        "//hpb/internal",
        "//hpb/internal:template_help",
        "//upb:mini_table",
    ],
)

cc_library(
    name = "interop",
    hdrs = ["interop.h"],
    visibility = [
        "//hpb:__subpackages__",
        "//src/google/protobuf/compiler:__subpackages__",
    ],
    deps = [
        "//hpb:ptr",
        "//hpb/internal",
        "//upb:mem",
        "//upb:message",
        "//upb:mini_table",
    ],
)

cc_test(
    name = "interop_test",
    srcs = ["interop_test.cc"],
    copts = UPB_DEFAULT_CPPOPTS,
    deps = [
        ":interop",
        "//src/google/protobuf/compiler/hpb/tests:test_model_upb_cc_proto",
        "//src/google/protobuf/compiler/hpb/tests:test_model_upb_proto",
        "//upb:mem",
        "//upb:message",
        "@com_google_googletest//:gtest",
        "@com_google_googletest//:gtest_main",
    ],
)
