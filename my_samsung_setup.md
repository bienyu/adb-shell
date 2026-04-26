### My Samsung device setup lists

```bash
# Settings > Battery > More battery settings > Performance profile > Light
# No adb command for this

# Speed up animations
adb shell settings put global animator_duration_scale 0.5
adb shell settings put global window_animation_scale 0.5
adb shell settings put global transition_animation_scale 0.5

# Enable dark mode
adb shell settings put secure night_mode 1

# Force 4G/LTE (Value 9 = LTE/GSM/WCDMA)
adb shell settings put global preferred_network_type 9

# Disable VoLTE
# People can't call you if your country doesn't have 2G/3G network or VoLTE support
adb shell settings put global volte_vt_enabled 0

# Disable adaptive battery
adb shell settings put global adaptive_battery_management_enabled 0

# Disable power saving mode
adb shell settings put global low_power 0

# Add apps to never sleep (whitelist)
# Gmail
adb shell cmd appops set com.google.android.gm RUN_IN_BACKGROUND allow
# Good Lock
adb shell cmd appops set com.samsung.android.goodlock RUN_IN_BACKGROUND allow

# Disable send diagnostic data
adb shell settings put global send_action_events 0

# Disable device scanning and network notifications
adb shell settings put global device_scanning_enabled 0
adb shell settings put global network_scan_enabled 0

# Disable Customization Service (Samsung)
# Settings > Samsung Account > Security and privacy > Customization service and toggle it off
# Also disable "Get news and special offers" & "Improve personalized advertising" in the bottom
adb shell pm disable-user --user 0 com.samsung.android.rubin.app

# Disable RAM plus
# Settings > Device care > Memory > RAM Plus > toggle it off

# Or using ADB below (not tested)
# Unlock the '0' option:
adb shell settings put global ram_expand_size_list 0,1,2,4,6,8
# Set the active size to '0':
adb shell settings put global ram_expand_size 0
# Reboot
adb reboot
```