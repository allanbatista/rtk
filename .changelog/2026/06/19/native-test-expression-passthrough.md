# Native Test Expression Passthrough

Date: 2026-06-19

## Changed

- Route `rtk test -d ...` and similar native `test` expressions to the system `test` command instead of `sh -c`.

## Files

- `src/main.rs`: detects native `test` expressions before using the RTK test-output wrapper.

## Validation

- `rtk cargo +1.91.0 fmt --all && rtk cargo +1.91.0 clippy --all-targets && rtk cargo +1.91.0 test --all`
- `rtk cargo +1.91.0 build`
- `rtk proxy ./target/debug/rtk test -d .`
- `rtk proxy ./target/debug/rtk test -d graphify-out`
- `rtk proxy ./target/debug/rtk test true`
