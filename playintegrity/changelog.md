> Release Date: 09/09/2025
> Source: Github

### NOTE: For those who are using ROM's inbuilt gms spoofing, pls create /data/adb/Box-Brain/gms  otherwise it’ll disable inbuilt pixel spoofing. Users who are using the PIF module can ignore this point.

- Added option to enable/disable pif advanced settings on action from webui (module settings)
- Disabled fetch fp with advanced settings during installation to pass strong without spoof provider on pixel spoofed ROMs
- Disabled keybox lock for seamless fetching
- Force update pushed, any previous version will no longer work
- Fixed auto update target list on boot not working
- Removed playstore auto update disabler leftover code
- Updated disable inbuilt spoofing related functions & fixed false positive webui indicator
- fixed internet check function not working during installation
- Updated keybox updater script
- Added option to hide TWRP detection
- Added option to fetch fingerprint on boot (internet is required)
- Added logging support for inbuilt spoofing related functions 
- Fixed spoof encryption not working when reset lineage props flag was enabled & added a separate toggle to control it
- Removed boot hash fixer shell script & its dependency on susfs, updated inbuilt fixer
- Removed PIF inject spoof script as it's webui already handles setting values
- Added action delay handler for ksu & apatch users
- Added lineage prop spoofing indicator in webui
- Dropped unnecessary deletions from cleanup script
- Fixed module description message not updating after notice update
- Nuked everything related to keybox from installation script, keybox updater script now handles it
- Dropped support for susfs
- Maybe something here & there. This is what i remember ;)

### A SHORT REMINDER 😉 
1) Always check play integrity from PlayStore's developer options
2) Uninstall playstore update if you're unable to pass 🟢🟢🟢 / or enable Spoof provider from PIF webui
3) You unlocked your bootloader to customize your device to your needs, not to fix every random detection that 90% of apps don’t even care about
4) Stop wasting time on unnecessary fixes & focus on what matters
