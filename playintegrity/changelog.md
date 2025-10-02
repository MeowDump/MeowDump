> Release Date: 03/10/2025
> Source: Github

- Added support to hide persist.sys.gphooks.enable & persist.sys.pphooks.enable detection using HIDE PIF DETECTION button
- Fixed internet check function not working on installation 
- Deprecated migrate.sh execution (pif fork)
- Reverted changes related to advanced settings 

### PIF fork WebUI:
- Improved auto-apply for toggles (Apply button removed, changes apply instantly).  
- Added backup/restore support for config using custom.pif.json.bak.  
- Added process killing support for both Play Service & Play Store, when restartMode=gms.  
- Added reboot option after saving when restartMode=reboot.  
- Centralized all paths and settings into a CONFIG object.  
- Toggle state now saved as JSON instead of key=value lines.  
- Improved sed regex for safer JSON field replacement.  
- Theme is now stored only in localStorage (no longer written to state file).  
- Popup notifications now batch display for all toggles in one save.  
- Removed Apply button and its functionality.  
- Removed secondary button style (btn.secondary).  
- Removed writing theme state into toggle_state.json.  
- Removed key=value style state file output.  
- Removed old popup CSS block (popup still works with shared styling).
  
### A SHORT REMINDER 😉 
1) Always check play integrity from PlayStore's developer options
2) Uninstall playstore update if you're unable to pass 🟢🟢🟢 / or enable Spoof provider from PIF webui
3) You unlocked your bootloader to customize your device to your needs, not to fix every random detection that 90% of apps don’t even care about
4) Stop wasting time on unnecessary fixes & focus on what matters
