```
$ bazel build --config=remote //proto:tonic_library
INFO: Invocation ID: 31f5bdd6-dd9f-4764-a700-72ca51fd3ace
INFO: Streaming build results to: https://app.buildbuddy.io/invocation/31f5bdd6-dd9f-4764-a700-72ca51fd3ace
INFO: Analyzed target //proto:tonic_library (178 packages loaded, 6115 targets configured).
INFO: Found 1 target...
ERROR: /workspaces/bazel-rbe-prost-error/proto/BUILD.bazel:11:14: Generating Rust protobuf stubs failed: (Exit 34): Invalid action cache entry 14590fa267dfc4c2555ba214be79a9ba7f8cf483ff0e5e28cf699e0087c1666a: expected output proto/tonic_library_generated/lib.rs does not exist.
Target //proto:tonic_library failed to build
Use --verbose_failures to see the command lines of failed build steps.
INFO: Elapsed time: 15.140s, Critical Path: 2.67s
INFO: 538 processes: 534 remote cache hit, 4 internal.
INFO: Streaming build results to: https://app.buildbuddy.io/invocation/31f5bdd6-dd9f-4764-a700-72ca51fd3ace
FAILED: Build did NOT complete successfully
```