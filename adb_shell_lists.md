# UI

### Speed up animations
```bash
adb shell settings put global animator_duration_scale 0.5
adb shell settings put global window_animation_scale 0.5
adb shell settings put global transition_animation_scale 0.5
```
### Disable animations
```bash
adb shell settings put global animator_duration_scale 0
adb shell settings put global window_animation_scale 0
adb shell settings put global transition_animation_scale 0
```
### Enable animations
```bash
adb shell settings put global animator_duration_scale 1
adb shell settings put global window_animation_scale 1
adb shell settings put global transition_animation_scale 1
```

### Enable dark mode
```bash
adb shell settings put secure night_mode 1
```

### Disable dark mode
```bash
adb shell settings put secure night_mode 0
``` 


# Network

### Force 4G/LTE
```bash
adb shell settings put global preferred_network_type 9
```

### Force 5G
```bash
adb shell settings put global preferred_network_type 20
```

### Force 3G
```bash
adb shell settings put global preferred_network_type 8
```

### Force 2G
```bash
adb shell settings put global preferred_network_type 7
```

### Disable VoLTE
```bash
adb shell settings put global volte_vt_enabled 0
```


# Battery and Power Saving

### Disable adaptive battery
```bash
adb shell settings put global adaptive_battery_management_enabled 0
```

### Enable adaptive battery
```bash
adb shell settings put global adaptive_battery_management_enabled 1
``` 

### Enable power saving mode
```bash
adb shell settings put global low_power 1
```

### Disable power saving mode
```bash
adb shell settings put global low_power 0
```

### Set to Light Performance Mode
```bash
# Note: There is no universal ADB command for this. Use:
# Settings > Battery > More battery settings > Performance profile > Light
```

### Disable RAM plus
```bash
# Step 1: Add '0' to the allowed size list
adb shell settings put global ram_expand_size_list 0,1,2,4,6,8

# Step 2: Set current size to 0
adb shell settings put global ram_expand_size 0

# Step 3: Reboot
adb reboot
```

### Enable RAM plus
```bash
# Set size to 4GB (example)
adb shell settings put global ram_expand_size 4
adb reboot
```


# App Management

### Add apps to never sleep (whitelist)
```bash
# adb shell cmd appops set <package_name> RUN_IN_BACKGROUND allow

# Gmail
adb shell cmd appops set com.google.android.gm RUN_IN_BACKGROUND allow
# Good Lock
adb shell cmd appops set com.samsung.android.goodlock RUN_IN_BACKGROUND allow
```

### Remove apps from never sleep (whitelist)
```bash
adb shell cmd appops set <package_name> RUN_IN_BACKGROUND default
```

### Add apps to restricted mode (battery restrictions)
```bash
adb shell cmd appops set <package_name> RUN_IN_BACKGROUND ignore
```

### Remove apps from restricted mode (battery restrictions)
```bash
adb shell cmd appops set <package_name> RUN_IN_BACKGROUND default
```


# Diagnostic, Scanning, and Customization


### Disable send diagnostic data
```bash
adb shell settings put global send_action_events 0
```

### Enable send diagnostic data
```bash
adb shell settings put global send_action_events 1
```

### Turn off device scanning and network notifications
```bash
adb shell settings put global device_scanning_enabled 0
adb shell settings put global network_scan_enabled 0
```

### Turn on device scanning and network notifications
```bash
adb shell settings put global ble_scan_always_enabled 1
adb shell settings put global wifi_scan_always_enabled 1
```

### Disable Customization Service (Samsung)

```bash
# Settings > Samsung Account > Security and privacy > Customization service and toggle it off
# Also disable "Get news and special offers" & "Improve personalized advertising" in the bottom
adb shell pm disable-user --user 0 com.samsung.android.rubin.app
```

### Enable Customization Service (Samsung)
```bash
adb shell pm enable com.samsung.android.rubin.app
```

### Disable Samsung Free (formerly Bixby Home)
```bash
adb shell pm disable-user --user 0 com.samsung.android.app.spage
```

### Enable Samsung Free (formerly Bixby Home)
```bash
adb shell pm enable com.samsung.android.app.spage
```