# Cursor AI Trial Reset Tool

This repository contains a PowerShell script that resets the machine identifiers used by Cursor AI to track trial usage. By resetting these identifiers, you can effectively restart your trial period.

## ⚠️ Disclaimer

This tool is provided for educational purposes only. Please respect the terms of service of software you use.

## What This Script Does

The script performs the following operations:
- Generates new unique machine identifiers
- Updates Cursor's machine ID configuration files
- Updates the SQLite database where Cursor stores machine information
- Changes the Windows Registry MachineGuid
- Creates backups of all modified files

## Features

- ✅ No external dependencies (except Python for SQLite operations)
- ✅ Creates backups of all modified files
- ✅ Completely transparent operation
- ✅ Does not run any external code from Cursor

## Prerequisites

- Windows operating system
- PowerShell
- Administrator privileges
- Python installed (optional, for SQLite database updates)

## How to Use

### Method 1: Download and Run

1. Make sure Cursor AI is closed
2. Download the `reset_cursor_windows.ps1` script
3. Right-click on PowerShell and select "Run as Administrator"
4. Navigate to the directory containing the script
5. Run the script:
   ```
   .\reset_cursor_windows.ps1
   ```
6. Launch Cursor AI after the script completes

### Method 2: Run Directly from PowerShell

1. Make sure Cursor AI is closed
2. Open PowerShell as Administrator
3. Run the following command:
   ```powershell
   Invoke-WebRequest -Uri "https://raw.githubusercontent.com/suryapaul01/Cursor-Trial-Reset/main/reset_cursor_windows.ps1" -OutFile "$env:TEMP\reset_cursor.ps1"; & "$env:TEMP\reset_cursor.ps1"
   ```

## Troubleshooting

If you encounter any issues:
- Ensure you're running PowerShell as Administrator
- Make sure Cursor is completely closed
- Check if Python is installed for SQLite operations
- Look for backup files if you need to restore the original configuration

## How It Works

The script resets various identifiers that Cursor uses to identify your machine:
1. The `machineId` file in Cursor's AppData directory
2. The `storage.json` file with various machine identifiers
3. The SQLite database that stores configuration data
4. The Windows Registry MachineGuid used by many applications

By changing these identifiers, the script makes your machine appear as a new device to Cursor.

## Contributing

Contributions, suggestions, and improvements are welcome! Feel free to open an issue or submit a pull request.
