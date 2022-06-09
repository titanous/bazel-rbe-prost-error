Failed remote invocation: https://app.buildbuddy.io/invocation/61cdea93-d227-40b1-94f6-74708293823a<br>
Successful local invocation: https://app.buildbuddy.io/invocation/a4af53aa-2e4a-48e0-916c-1f798594517f

```
$ bazel build --config=remote //proto:tonic_library
2022/06/09 16:11:57 Downloading https://releases.bazel.build/5.2.0/release/bazel-5.2.0-linux-x86_64...
Extracting Bazel installation...
Starting local Bazel server and connecting to it...
INFO: Invocation ID: 61cdea93-d227-40b1-94f6-74708293823a
INFO: Streaming build results to: https://app.buildbuddy.io/invocation/61cdea93-d227-40b1-94f6-74708293823a
INFO: Analyzed target //proto:tonic_library (178 packages loaded, 6132 targets configured).
INFO: Found 1 target...
ERROR: /workspaces/bazel-rbe-prost-error/proto/BUILD.bazel:11:14: Generating Rust protobuf stubs failed: (Exit 34): Invalid action cache entry cb3d599368c5eded7ba5eee92073da64e00266b5d95af8f942168bc806d18ab9: expected output proto/tonic_library_generated/lib.rs does not exist.
Target //proto:tonic_library failed to build
Use --verbose_failures to see the command lines of failed build steps.
INFO: Elapsed time: 145.143s, Critical Path: 91.43s
INFO: 666 processes: 133 internal, 533 remote.
INFO: Streaming build results to: https://app.buildbuddy.io/invocation/61cdea93-d227-40b1-94f6-74708293823a
FAILED: Build did NOT complete successfully

$ bazel build //proto:tonic_library
INFO: Streaming build results to: https://app.buildbuddy.io/invocation/a4af53aa-2e4a-48e0-916c-1f798594517f
INFO: Build options --crosstool_top, --define, --experimental_inmemory_dotd_files, and 6 more have changed, discarding analysis cache.
INFO: Analyzed target //proto:tonic_library (2 packages loaded, 6118 targets configured).
INFO: Found 1 target...
Target //proto:tonic_library up-to-date:
  bazel-bin/proto/libtonic_library-984845105.rlib
INFO: Elapsed time: 405.914s, Critical Path: 146.51s
INFO: 670 processes: 131 internal, 539 linux-sandbox.
INFO: Streaming build results to: https://app.buildbuddy.io/invocation/a4af53aa-2e4a-48e0-916c-1f798594517f
INFO: Build completed successfully, 670 total actions
```