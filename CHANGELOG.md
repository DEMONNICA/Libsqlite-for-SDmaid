> `Changelog:`
> - All significant changes to this project will be documented here.
---

> [3.53.0] - `2026-04-09`
>
> - Updated `libsqlite3.so` to the latest version `3.53.0`.
> - Updated `README.md` feature list to reflect current extraction behavior.
> - Fixed `post_install_actions` missing `NAME_MODULE` definition.
> - Fixed `local var=$(...)` declarations for better shell compatibility.
> - Improved `customize.sh` ABI detection with `getprop` as primary and `uname -m` as fallback.
> - Improved `verify.sh` with `clean_path()` sanitization and multi-algorithm hash verification support.
> - Removed `SKIPUNZIP=1` and `DEBUG=false` from `customize.sh`.
> - Added `FolkLite` (`mi.yuki.folk`) detection in APatch section.
> - Added numbered comments throughout `customize.sh` for better readability.
---

> [3.51.3] - `2026-03-13`
>
> - License Changes.
> - Changed the structure of `README.md` for a better impression.
> - Updated `libsqlite3.so` to the latest version `3.51.3`.
> - Updated module `description` for better clarity.
> - Updated `customize.sh` and `verify.sh` for better future performance.
> - Improved `customize.sh` ABI detection and file extraction based on architecture.
> - Simplified `libsqlite_prjkt()` using `find` instead of hardcoded ABI folder names.
> - Updated `set_permissions()` to use `find` loop for better permission handling.
> - Added `service.sh` with post-boot DEX optimization and process priority tuning.
> - Added `uninstall.sh` with DEX reset, fstrim, sync, and module cleanup.
> - Added messaging-style notification in `service.sh` after library verification.
> - Added comments throughout all scripts for better readability.
---

> [3.51.2] - `2026-01-09`
>
> - Updated `libsqlite3.so` to the latest version `3.51.2`.
> - Improved `detect_root_all` code and some changes and fixes in `customize.sh`.
> - Code changes in `verify.sh` for stronger module security improvements.
> - And other improvements that may be better than the previous version.
---