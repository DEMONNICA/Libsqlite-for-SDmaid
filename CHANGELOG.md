> `Changelog:`
> - All significant changes to this project will be documented here.
---

> [3.51.0] - `2025-11-04`
>
> - Simplified `display_device_info` in `customize.sh` by removing `device_capitalized` variable and directly printing device/model info without capitalization.
> - Removed `display_ram_info`, `android_version_check`, `architecture_check`, `module_remove_check`, and `sqlite_prjkt` functions from `customize.sh` for streamlined installation flow.
> - Updated `extract_files` in `customize.sh` to include extraction of documentation files (`CHANGELOG.md`, `README.md`, `LICENSE`) alongside architecture-specific binaries (`aarch64.so`, `armv7a.so`, `x86_64.so`, `x86.so`).
> - Modified `set_permissions` in `customize.sh` to only apply executable permissions to `service.sh`, removing references to other EXEC_FILES.
> - Increased random devil-themed messages to 15 variants in `print_random_devil_message` and simplified `ui_print` messages to single-word devil names without descriptions.
> - Simplified `detect_abi` in `service.sh` by removing `dst_arch` variable and focusing solely on `src_arch` detection.
> - Updated binary copying logic in `service.sh` to source from `$MODDIR/$src_arch.so` and copy directly to `libsqlite3.so`.
> - Changed destination directory detection in `service.sh` to locate based on `libtoybox.so` path instead of fixed `$app_dir/lib/$dst_arch`.
> - Removed `set -e` and changed shebang from `#!/system/bin/sh` to `#!/bin/sh` in `service.sh` for broader compatibility.
> - Removed initial command availability checks (`for cmd in unzip sha1sum ...`) in `verify.sh` as they are now assumed available.
> - General code cleanup: improved error handling, removed redundant variables, enhanced fallback logic in ABI detection, and ensured consistent formatting across scripts.
---