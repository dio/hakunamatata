licenses(["notice"])  # Apache 2

load(
    "//bazel:envoy_build_system.bzl",
    "envoy_package",
)
load(
    "//test/extensions:extensions_build_system.bzl",
    "envoy_extension_cc_mock",
    "envoy_extension_cc_test",
)

envoy_package()

envoy_extension_cc_test(
    name = "matchers_test",
    srcs = ["matchers_test.cc"],
    extension_name = "envoy.filters.http.rbac",
    deps = [
        "//source/extensions/filters/common/rbac:matchers_lib",
        "//test/mocks/network:network_mocks",
        "//test/mocks/ssl:ssl_mocks",
        "//test/test_common:utility_lib",
        "@envoy_api//envoy/api/v2/core:pkg_cc_proto",
        "@envoy_api//envoy/api/v2/route:pkg_cc_proto",
        "@envoy_api//envoy/config/rbac/v2:pkg_cc_proto",
        "@envoy_api//envoy/type/matcher:pkg_cc_proto",
    ],
)

envoy_extension_cc_test(
    name = "engine_impl_test",
    srcs = ["engine_impl_test.cc"],
    extension_name = "envoy.filters.http.rbac",
    deps = [
        "//source/extensions/filters/common/rbac:engine_lib",
        "//test/mocks/network:network_mocks",
        "//test/mocks/ssl:ssl_mocks",
        "//test/mocks/stream_info:stream_info_mocks",
        "//test/test_common:utility_lib",
        "@envoy_api//envoy/api/v2/core:pkg_cc_proto",
        "@envoy_api//envoy/config/rbac/v2:pkg_cc_proto",
    ],
)

envoy_extension_cc_mock(
    name = "engine_mocks",
    hdrs = ["mocks.h"],
    extension_name = "envoy.filters.http.rbac",
    deps = [
        "//source/extensions/filters/common/rbac:engine_lib",
        "@envoy_api//envoy/config/rbac/v2:pkg_cc_proto",
    ],
)
