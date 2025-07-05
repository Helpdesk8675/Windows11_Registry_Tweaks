# Overview

# Windows Registry Changes and Their Impact

## Performance & Startup Optimizations

### Disable Startup Delay
**Registry Path:** `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer`
**Change:** `StartupDelayInMSec` = `0`
**Impact:** Eliminates the artificial delay Windows adds when starting up, making boot times faster by removing unnecessary wait times.

### Disable Startup Sound
**Registry Path:** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Authentication\LogonUI\BootAnimation`
**Change:** `DisableStartupSound` = `1`
**Impact:** Prevents Windows from playing the startup sound during boot, creating a quieter boot experience and potentially reducing boot time slightly.

## Privacy & Search Modifications

### Remove Bing Search Suggestions from Start Menu
**Registry Path:** `HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\Explorer`
**Change:** `DisableSearchBoxSuggestions` = `1`
**Impact:** Disables web search suggestions in the Start Menu search, keeping searches local to your computer and improving privacy by preventing data from being sent to Microsoft's servers.

### Disable Windows Copilot
**Registry Paths:** Multiple paths related to Copilot functionality
**Changes:** 
- `IsCopilotAvailable` = `0`
- `IsUserEligible` = `0`
- `AllowCopilotRuntime` = `0`
- `ShowCoPilotButton` = `0`
**Impact:** Completely disables Windows Copilot AI assistant, removing the button from the taskbar and preventing the feature from running, which can improve system performance and privacy.

## User Interface Customizations

### Show This PC Icon on Desktop
**Registry Path:** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\HideDesktopIcons\NewStartPanel`
**Change:** `{20D04FE0-3AEA-1069-A2D8-08002B30309D}` = `0`
**Impact:** Makes the "This PC" icon visible on the desktop, providing quick access to drives and system folders without needing to open File Explorer.

### Set Taskbar to Left Alignment (Windows 11)
**Registry Path:** `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced`
**Change:** `TaskbarAl` = `0`
**Impact:** Changes the taskbar alignment from center (Windows 11 default) to left alignment, mimicking the classic Windows layout that many users prefer.

### Enable File Extensions in Explorer
**Registry Path:** `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced`
**Change:** `HideFileExt` = `0`
**Impact:** Shows file extensions for all files in Windows Explorer, making it easier to identify file types and improving security by revealing potentially malicious file extensions.

### Classic Context Menu (Disable Compact Context Menu)
**Registry Path:** `HKEY_CURRENT_USER\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}` and `{d93ed569-3b3e-4bff-8355-3c44f6a52bb5}`
**Change:** Creates empty InprocServer32 entries
**Impact:** Restores the classic Windows 10-style context menu in Windows 11, replacing the simplified context menu with the full traditional menu that shows all options immediately.

## System Features

### Restore Sleep Timeout in Power Options
**Registry Path:** `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\238c9fa8-0aad-41ed-83f4-97be242c8f20\9d7815a6-7ee4-497e-8888-515a05f02364`
**Change:** `Attributes` = `2`
**Impact:** Makes sleep timeout settings visible in Power Options, allowing users to configure when their computer goes to sleep (this option is hidden by default in some Windows versions).

### Add Hash Context Menu for Files
**Registry Path:** `HKEY_LOCAL_MACHINE\SOFTWARE\Classes\*\shell\hash`
**Changes:** Creates comprehensive hash calculation menu with multiple algorithms
**Impact:** Adds a "Hash" submenu to the right-click context menu for all files, allowing users to quickly calculate file hashes using various algorithms (SHA1, SHA256, SHA384, SHA512, MACTripleDES, MD5, RIPEMD160). This is useful for:
- Verifying file integrity
- Security analysis
- Detecting file modifications
- Compliance with security requirements
