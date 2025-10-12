> Release Date: 12/10/2025
> Source: Github

## NOTICE: Kindly use the latest PIF Fork from workflow run (check telegram channel). The latest PIF fork release version you're using is not compatible with v24


### ACTION.SH

- Pre-Execution Safety Checks
  - Introduced `override` flag handling to run `override_lineage.sh` and exit

- Google Wallet Detection
  - Added package check for `com.google.android.apps.walletnfcrel`
  - Spoofing changes now skipped if Wallet is present, avoiding NFC issues

- Network Connectivity Enhancements
  - Increased retry attempts from 5 to 10 with exponential backoff capped at 30s
  - Connection attempts, failures, and retries are logged for transparency

- Logging System
  - Added `/data/adb/Box-Brain/Integrity-Box-Logs/spoofing.log` for centralized logging related to spoofing 
  - Created `log()` function for timestamped entries
  - Added `setval()` function to update key-values with logging

- Fingerprint Update Logic
  - Advanced mode triggers `autopif2.sh` with `-s -m -p`
  - Standard mode falls back to `autopif2.sh` or `autopif.sh` if available
  - Status output is now more descriptive: UPDATED, FAILED, MISSING

- Advanced Spoofing Props Control
  - Applies spoofing props only if Wallet is absent and advanced flag is present
  - Backs up `custom.pif.prop` before modifications
  - Updates recommend spoof keys using `setval`

- Automatic Cleanup of Advanced JSON Settings
  - Removes advanced spoof entries and verboseLogs if advanced flag is missing
  - Displays CLEANED status
  - Prevents leftover advanced configuration

- Boot Patch Script Support
  - Added execution support for `patch.sh` with status handling

- Improved Status Labels
  - Replaced generic OK/FAIL with UPDATED, FAILED, MISSING, KILLED, SKIPPED, BACK-UP, CLEANED

- Wallet-Aware Skipping Logic
  - Spoofing is skipped if Wallet detected or advanced flag missing


### POST FS DATA.SH

- Placeholder File Updates
  - Renamed placeholders to remove `.sh` extension
    - `meowverse.sh` to `meowdump`
    - `boot_hash.sh` to `boot_hash`
    - `vending.sh` to `vending`
    - `report.sh` to `report`
    - `start.sh` to `start`
    - `stop.sh` to `stop`
  - Removed unused `sus.sh` script

- Override Lineage Props
  - Added creation logic for `override_lineage.sh` in `webroot/common_scripts` if missing
  - Implements clearing override flag, logging start/end, reading `system.prop`, skipping restricted props, overriding via `resetprop`, verifying values, marking execution via `.los`

- Hash.sh Improvements
  - Cleaner logging and startup messages
  - Simplified resetprop detection via dedicated variable
  - Applied static VBMeta props unconditionally
  - Improved hash validation and digest handling
  - Cleaner exit flow with structured logging


### SERVICE.SH

- Removed Delays
  - Removed redundant `sleep 69` before description script and `user.sh`

- Logging Clarity
  - Updated encryption log: "Added line: $LINE" to "Spoofed prop: $LINE"
  - Updated TWRP rename header to "TWRP/FOX RENAME"

- Fox Recovery Handling
  - Added `rename_recovery_folder` function
  - Supports marker `/data/adb/Box-Brain/fox` and folders `/sdcard/Fox`
  - Renames or deletes Fox recovery folder like TWRP

- Robust Folder Resolution
  - Falls back to alternate paths if main path not found
  - Skips execution if neither path exists or marker missing

- Code Cleanup
  - Removed unnecessary blank lines and echoes
  - Added spacing and formatting for readability



### UNINSTALL.SH

- Removed residual directories and files: `/data/adb/Box-Brain`, `keybox.xml`, `target.txt`, Shamiko/NoHello whitelists, PlayIntegrity module
- Restores backups if `.bak` files exist
- Reverts system properties: `persist.sys.pihooks.disable.gms_key_attestation_block`, `persist.sys.pihooks.disable.gms_props`, `persist.sys.pihooks.disable`, `persist.sys.kihooks.disable`
- Logs all actions in `/sdcard/uninstall.log`
- Ensures filesystem sync to prevent leftover changes



### INDEX.HTML

- Updated language dropdown labels for clarity
- Updated button `data-script` attributes to match new file structure
  - `boot_hash` to `boot_hash.sh`
  - `start.sh` to `start`
  - `stop.sh` to `stop`
  - `meowdump.sh` to `meowdump`
  - `report.sh` to `report`
  - `vending.sh` to `vending`
- Language rebase


### MODULE SETTINGS

- Added **Override Lineage Props** option to force system properties
- Remembers option state across reboots
- Added popup 



### PLAY INTEGRITY FORK

- UI & Theme
  - Simplified and modernized interface
  - Light/dark mode toggle applies globally
  - Improved color contrast and smoother button/toggle animations

- New Toggles / Features
  - Spoof Vending Finger toggle for enhanced fp spoofing
  - Verbose Logs toggle for detailed debugging
  - Toggle states persist across sessions

- Behavior & Functionality
  - Safe configuration updates without breaking the module
  - Added Restart button 
  - Config checks across multiple paths for reliability
  - Async/await and centralized shell execution for safer, faster operations



### APP.SH

- Updated risky apps list: added `com.dergoogler.mmrl.wx` and `com.dergoogler.mmrl`
- Consolidated logging into structured blocks (Package + Status)
- Marked spoofed apps with `SPOOFED`, preventing duplicates
- Trimmed version names to ensure accurate detection
- Simplified detection logic; merged results into `FOUND_APPS`
- Updated guidance message to reference Hide My Applist (LSPosed module)
- Logs consistently include scan start, detected apps, completion, and log file location



### CLEANUP.SH

- Removed references to BOX/BOX2 variables and IntegrityBox directories
- Removed uninstall commands for apps: `meow.helper`, `popup.toast`, `imagine.detecting.ablank.app`
- Removed module.prop remove flags and directories (`AntiBloat`, `PixelLauncher`, `PowerSaverPro`, `integrity_box`, `zygisk`)
- Moved check for `IntegrityBox.png` to end of script
- Simplified cleanup, removing only known leftover files and keybox modifications



### KEY.SH

- Clarified verification comment to “virtual” verification instead of generic “local verify matches remote”



### PATCH.SH

- Updated patch date to `2025-09-05` with `PATCH_DATE` and `HUMAN_DATE`
- Logging now appends directly to `$LOG`
- Logs Patch Date and Applied On with standardized timestamps
- Added existence checks for `$TARGET_DIR`
- Added error handling for writing `$FILE_CONTENT` to `$FILE_PATH`
- Removed old hardcoded patch date and console echo



### PIF.SH

- Renamed custom fingerprint files from `.json` to `.prop` (source & destination)
- Updated all related file checks and copy operations to use `.prop`



### USER.SH

- Added `set -e` to exit on error
- Introduced `CAND` temp file for candidate packages from `pm list`, `packages.list`, and `packages.xml`
- Added `CORE_PKGS` for essential packages
- Added `BLOCKLIST` to filter system apps, overlays, and ROM-specific packages
- Centralized deduplication and blocklist filtering
- Added TMP_CLEAN for pre-final cleanup
- Enforced `chmod 600` and `chown root:root` on target file
- Streamlined cleanup using `trap cleanup EXIT INT TERM HUP`
- Removed verbose backup and banner messages; final target list output is clean
