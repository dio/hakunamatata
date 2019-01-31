licenses(["notice"])  # Apache 2

load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_mock",
    "envoy_cc_test",
    "envoy_package",
)

envoy_package()

envoy_cc_mock(
    name = "aws_mocks",
    srcs = ["mocks.cc"],
    hdrs = ["mocks.h"],
    deps = [
        "//source/extensions/filters/http/common/aws:credentials_provider_interface",
        "//source/extensions/filters/http/common/aws:signer_interface",
    ],
)

envoy_cc_test(
    name = "signer_impl_test",
    srcs = ["signer_impl_test.cc"],
    deps = [
        "//source/common/buffer:buffer_lib",
        "//source/common/http:message_lib",
        "//source/extensions/filters/http/common/aws:signer_impl_lib",
        "//test/extensions/filters/http/common/aws:aws_mocks",
        "//test/test_common:simulated_time_system_lib",
        "//test/test_common:utility_lib",
    ],
)

envoy_cc_test(
    name = "utility_test",
    srcs = ["utility_test.cc"],
    deps = [
        "//source/extensions/filters/http/common/aws:utility_lib",
        "//test/test_common:utility_lib",
    ],
)