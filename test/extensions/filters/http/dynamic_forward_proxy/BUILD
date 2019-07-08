licenses(["notice"])  # Apache 2

load(
    "//bazel:envoy_build_system.bzl",
    "envoy_package",
)
load(
    "//test/extensions:extensions_build_system.bzl",
    "envoy_extension_cc_test",
)

envoy_package()

envoy_extension_cc_test(
    name = "proxy_filter_test",
    srcs = ["proxy_filter_test.cc"],
    extension_name = "envoy.filters.http.dynamic_forward_proxy",
    deps = [
        "//source/extensions/filters/http/dynamic_forward_proxy:config",
        "//test/extensions/common/dynamic_forward_proxy:mocks",
        "//test/mocks/http:http_mocks",
        "//test/mocks/upstream:upstream_mocks",
    ],
)

envoy_extension_cc_test(
    name = "proxy_filter_integration_test",
    srcs = ["proxy_filter_integration_test.cc"],
    extension_name = "envoy.filters.http.dynamic_forward_proxy",
    deps = [
        "//source/extensions/clusters/dynamic_forward_proxy:cluster",
        "//source/extensions/filters/http/dynamic_forward_proxy:config",
        "//test/integration:http_integration_lib",
    ],
)