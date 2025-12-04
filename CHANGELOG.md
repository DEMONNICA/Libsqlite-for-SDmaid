> `Changelog:`
> - All significant changes to this project will be documented here.
---

> [3.51.1] - `2025-11-28`
>
> - Updated `libsqlite3.so` to the latest version `3.51.1`.
> - Removed the `[REBUILD]` section in module.prop.
> - Changed the module banner for `KSUN` users.
> - Moved the function from `run.sh` to `customize.sh and removed the code section to run `run.sh` in `service.sh`.
> - And a few code changes I didn't mention.
---

> [3.51.0] - `2025-11-04`
>
> - Enhanced APatch detection in `customize.sh` and `service.sh` with detailed version fetching: VAPK from `dumpsys package`, VKER from GitHub API `curl`, and storage in `/data/adb/ap/kernelver` for consistent `ROOT_VERSION` formatting.
> - Added `display_ram_info` function in `customize.sh` to log available and total RAM using `free -h`.
> - Updated `display_device_info` in `customize.sh` to include full model name and capitalized device code for better logging.
> - Added `android_version_check` in `customize.sh` to detect and display Android version with SDK codenames (e.g., Q, R, S) and corresponding emojis.
> - Introduced `architecture_check` in `customize.sh` to print device architecture using `getprop ro.product.cpu.abi` or `uname -m`.
> - Expanded `extract_files` in `customize.sh` to handle extraction of multiple architecture-specific binaries (`aarch64.so`, `armv7a.so`, `x86_64.so`, `x86.so`) alongside other files like `service.sh`, `run.sh`, `uninstall.sh`, `README.md`, and `LICENSE`.
> - Increased random devil-themed messages to 15 variants in `print_random_devil_message` in `customize.sh` with a more concise single-line `case` statement.
> - Renamed and refactored `print_time` to `display_current_time` and `print_device` to `display_device_info` in `customize.sh` for consistency.
> - Moved core logic from `service.sh` (old) to a new `run.sh` script, which now handles ABI detection, binary copying with fallback to BusyBox, and prioritizes `libtoybox.so` path for placement.
> - Updated `service.sh` to include a random emoji generator for updating the `author` field in `module.prop` (e.g., `@illumi (smiling face with tongue)`).
> - Modified `service.sh` to append `[REBUILD]` to version in `module.prop` only if not already present, and wait for boot completion with a 120-second timeout before executing `run.sh` via `nohup`.
> - Enhanced ABI detection in `run.sh` to consolidate `armeabi-v7a` and `armeabi` under `armv7a`, and added fallback copying using `busybox cp` if standard `cp` fails.
> - Added post-install compilation with `pm compile -f -m speed` for the target package in `run.sh` to optimize performance.
> - Removed initial command availability checks (`unzip`, `sha256sum`, etc.) in `verify.sh` as they are assumed present.
> - Enhanced `extract` function in `verify.sh` with multi-algorithm hash support (`sha512`, `sha384`, `sha256`, `sha224`, `sha1`) and automatic fallback, including detailed error messages with expected and actual hashes.
> - General code cleanup: improved variable handling, added error exits, ensured compatibility with various architectures, and refined installation notifications and permissions in `customize.sh`.
---