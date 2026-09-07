> `Changelog:`
> - All significant changes to this project will be documented here.
---

> [3.53.4] - `2026-07-24`
>
> - Added `VortexSU` and `Kokoro Mask` detection in `detect_root_all`.
> - Added `aapt`-based spoofed variant detection fallback before generic `ksud` detection in `detect_root_all`.
> - Added cache directory cleanup in `uninstall.sh` — removes leftover files from `/data/cache`, `/data/dalvik-cache`, `/data/resource-cache`, `/data/system/dropbox`, `/data/tombstones`, and `/data/local/tmp`.
> - Added `detect_sdmaid` in `customize.sh` — aborts installation if SD Maid is not installed on the device.
> - Added author verification in `verify.sh` — checks `author=` field in `module.prop` against `@illumi`.
> - Changed module banner image in `README.md`.
> - Changed `device_info` RAM labeling from inline `if/elif` chain to a reusable `ram_label()` helper function.
> - Changed `detect_root_all` to loop-based detection instead of `if/elif` chain.
> - Changed `detect_root_all` order to APatch → KernelSU → Magisk.
> - Changed `libsqlite3.so` to the latest version `3.53.4`.
> - Changed ABI detection to a single `case` statement directly from `getprop`, removing `uname -m` fallback and all aliases.
> - Fixed `verify.sh` stripping spaces from ZIP path via `clean_path()`, causing installation failure on modules with spaces in filename.
> - Removed `hjggum.uaqona.iogbgn` from KernelSU Next detection in `detect_root_all`.
---

> [3.53.0] - `2026-04-09`
>
> - Added `FolkLite` (`mi.yuki.folk`) detection in APatch section.
> - Added numbered comments throughout `customize.sh` for better readability.
> - Changed `libsqlite3.so` to the latest version `3.53.0`.
> - Changed `README.md` feature list to reflect current extraction behavior.
> - Changed `service.sh` boot wait interval from `3s` to `30s` for better stability.
> - Changed `customize.sh` ABI detection with `getprop` as primary and `uname -m` as fallback.
> - Changed `verify.sh` with `clean_path()` sanitization and multi-algorithm hash verification support.
> - Fixed `post_install_actions` missing `NAME_MODULE` definition.
> - Fixed `local var=$(...)` declarations for better shell compatibility.
> - Removed `SKIPUNZIP=1` and `DEBUG=false` from `customize.sh`.
> - Removed redundant `sleep 5` after boot completion check in `service.sh`.
---

> [3.51.3] - `2026-03-13`
>
> - Added `service.sh` with post-boot DEX optimization and process priority tuning.
> - Added `uninstall.sh` with DEX reset, fstrim, sync, and module cleanup.
> - Added messaging-style notification in `service.sh` after library verification.
> - Added `WeaveMask` (`io.github.seyud.weave`) detection in Magisk section.
> - Added comments throughout all scripts for better readability.
> - Changed the structure of `README.md` for a better impression.
> - Changed module `description` for better clarity.
> - Changed `customize.sh` and `verify.sh` for better future performance.
> - Changed `customize.sh` ABI detection and file extraction based on architecture.
> - Changed `libsqlite_prjkt()` using `find` instead of hardcoded ABI folder names.
> - Changed `set_permissions()` to use `find` loop for better permission handling.
> - Changed license from GNU General Public License to Apache License 2.0.
> - Removed backup and restore logic from `customize.sh`.
---

> [3.51.2] - `2026-01-09`
>
> - Changed `detect_root_all` detection code and various fixes in `customize.sh`.
> - Changed `libsqlite3.so` to the latest version `3.51.2`.
> - Changed `verify.sh` with stronger module security enhancements.
---

> [3.51.1] - `2025-11-28`
>
> - Changed `libsqlite3.so` to the latest version `3.51.1`.
> - Changed module banner image for KernelSU Next users in `README.md`.
> - Changed function from `run.sh` into `customize.sh` and removed the code section to run `run.sh` in `service.sh`.
> - Removed the `[REBUILD]` section in `module.prop`.
---

> [3.51.0] - `2025-11-04`
>
> - Added `display_ram_info` function in `customize.sh` to log available and total RAM using `free -h`.
> - Added `android_version_check` in `customize.sh` to detect and display Android version with SDK codenames and corresponding emojis.
> - Added `architecture_check` in `customize.sh` to print device architecture using `getprop ro.product.cpu.abi` or `uname -m`.
> - Added post-install compilation with `pm compile -f -m speed` for the target package in `run.sh` to optimize performance.
> - Changed APatch detection in `customize.sh` and `service.sh` with detailed version fetching: VAPK from `dumpsys package`, VKER from GitHub API `curl`.
> - Changed `display_device_info` in `customize.sh` to include full model name and capitalized device code for better logging.
> - Changed `extract_files` in `customize.sh` to handle extraction of multiple architecture-specific binaries alongside other files.
> - Changed random devil-themed messages to 15 variants in `print_random_devil_message` with a more concise single-line `case` statement.
> - Changed `print_time` to `display_current_time` and `print_device` to `display_device_info` in `customize.sh` for consistency.
> - Changed core logic from `service.sh` to a new `run.sh` script, which handles ABI detection, binary copying with fallback to BusyBox, and prioritizes `libtoybox.so` path.
> - Changed `service.sh` to include a random emoji generator for updating the `author` field in `module.prop`.
> - Changed `service.sh` to append `[REBUILD]` to version in `module.prop` only if not already present, and wait for boot completion with a 120-second timeout before executing `run.sh` via `nohup`.
> - Changed ABI detection in `run.sh` to consolidate `armeabi-v7a` and `armeabi` under `armv7a`, and added fallback copying using `busybox cp` if standard `cp` fails.
> - Changed `extract` function in `verify.sh` with multi-algorithm hash support (`sha512`, `sha384`, `sha256`, `sha224`, `sha1`) and automatic fallback.
> - Changed general code structure — variable handling, error exits, architecture compatibility, and installation notifications in `customize.sh`.
> - Removed initial command availability checks (`unzip`, `sha256sum`, etc.) in `verify.sh` as they are assumed present.
---

> [3.50.4] - `2025-07-30`
>
> - Added random emoji to author field in `module.prop`.
> - Added compilation optimization with `pm compile -f -m speed` for target package.
> - Added process priority adjustments with `renice` and `ionice` for running target package.
> - Added device info (manufacturer, model, kernel) and RAM details (total, available) display during installation.
> - Added Android version codenames and minimum SDK check with detailed error messages.
> - Added new devil-themed message: "Beelzebub: The Gluttony Magic Devil."
> - Added post-install actions for Telegram link and success notification.
> - Added explicit `exit 0` at the end of `service.sh` for clean termination.
> - Changed root detection for APatch to include APK version via `dumpsys` and kernel version from GitHub.
> - Changed module removal logic to fail immediately on error.
> - Changed module verification to check author, name, and ID strictly.
> - Changed file extraction list, separating architecture-specific `.so` files.
> - Changed hash support in `verify.sh` to include SHA1, SHA224, SHA256, SHA384, SHA512.
> - Changed checksum mismatch error to show expected and actual hashes.
> - Changed module banner image in `README.md`.
---

> [3.50.4] - `2025-07-30`
>
> - Changed minimum supported Android version to Android 10+.
> - Changed code section in `customize.sh`.
> - Changed `verify.sh` hash verification.
> - Changed `libsqlite3.so` to the latest version `3.50.4`.
> - Changed code in `service.sh`.
---

> [3.49.1] - `2025-02-18`
>
> - Changed `README.md` for a more professional look.
> - Fixed typo in `customize.sh`.
---

> [3.49.1] - `2025-02-18`
>
> - Added module banner image for KernelSU Next in `README.md`.
> - Changed code for better optimization and readability.
> - Changed module banner image in `README.md`.
---

> [3.49.1] - `2025-02-18`
>
> - Added `verify.sh` for module file integrity.
> - Added boot timeout protection — 300-second timeout prevents infinite waiting for boot completion.
> - Added installation counter to track and validate successful library deployments.
> - Changed `customize.sh` with dynamic module directory detection using its own location instead of hardcoded path.
> - Changed architecture support with added aliases.
> - Changed error handling with early exit conditions for better failure detection.
> - Changed package validation to verify target package exists before processing.
> - Changed file operations with better error checking and handling for copy operations.
> - Changed code structure — removed unused variables and simplified conditional logic.
> - Removed logging system — eliminated log file creation and detailed logging for cleaner execution.
> - Removed notification system — no more Android notification popups during deployment process.
> - Removed module property parsing — no longer reads module name from `module.prop`.
---

> [3.49.1] - `2025-02-18`
>
> - Added log storage in `/data/adb/modules/SDMAID`.
> - Changed `libsqlite3.so` to version `3.49.1`.
> - Changed module banner image in `README.md`.
---

> [3.49.0] - `2025-02-06`
>
> - Initial release.
---