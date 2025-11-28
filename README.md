
# 🏃 AddToRun - Program Alias Manager

**AddToRun** is a lightweight Windows utility that allows you to create custom "aliases" for your favorite programs. Once an alias is created, you can launch that program instantly from the Windows Run dialog (`Win + R`) by typing your custom keyword.

For example, map `C:\Program Files\Notepad++\notepad++.exe` to `np`. Now, simply type `np` in the Run box to launch it!

## ✨ Features

*   **Simple GUI:** Clean, modern interface using native Windows controls (Segoe UI).
*   **Drag & Drop:** Drag any executable file into the window to instantly load its path and auto-suggest an alias.
*   **Context Menu Integration:** Adds a "Create/Set Alias" option to the right-click menu of any executable file.
*   **Architecture Aware:** Automatically detects 64-bit vs 32-bit Windows environments and writes to the correct Registry View.
*   **Safety Checks:** Prevents overwriting existing system commands without warning and validates file paths.
*   **Portable:** Compiles to a single executable with no external dependencies.

## 🚀 How It Works

Windows allows applications to register "App Paths" in the Registry. When you type a command into the Run dialog, Windows checks this registry key to find the executable associated with that command.

**AddToRun** automates the process of writing to:
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\App Paths\`

## 📖 Usage

### Method 1: The GUI
1.  Run `AddToRunExtended.exe` (Administrator privileges required).
2.  Click **Browse** to select a program, or simply **Drag & Drop** an `.exe` file into the window.
3.  Type your desired short name in the **Alias Name** box (e.g., `firefox`, `code`, `shop`).
4.  Click **Add Alias**.

### Method 2: Context Menu
1.  Open the application and click **Add to Context Menu**.
2.  Navigate to any program in File Explorer.
3.  **Right-click** the file and select **Create/Set Alias with AddToRun**.
4.  The application opens with the file path already pre-loaded.

## 🛠️ Compilation & Development

If you wish to modify or compile the script yourself, you will need **AutoIt v3**.

### Prerequisites
*   [AutoIt v3](https://www.autoitscript.com/site/autoit/) installed.
*   [SciTE4AutoIt3](https://www.autoitscript.com/site/autoit-script-editor/) (Recommended for the Wrapper directives).
*   An icon file named `app.ico` in the script directory.

### Compiling
The script uses `#AutoIt3Wrapper` directives to handle resource embedding (including the icon).

1.  Open `AddToRun.au3` in SciTE.
2.  Press `F7` (Build).
3.  The wrapper will embed `app.ico` into the final EXE and compress it using UPX.

**Note on Icon Handling:**
The script uses `FileInstall` to embed the icon. When running as a compiled EXE, it extracts the icon to the `%TEMP%` directory to use it for the GUI window and Context Menu registry keys.

## ⚠️ Technical Notes

*   **Privileges:** Because this tool modifies `HKEY_LOCAL_MACHINE`, it requires **Administrative Privileges** to run. The script includes `#RequireAdmin` to prompt for UAC automatically.
*   **Path Limits:** The tool checks for paths exceeding ~250 characters, as older versions of Windows have issues with long App Paths.

## 📄 License

**Copyleft © 2024 Halftime Software**
You are free to use, modify, and distribute this software.

***

*Made with AutoIt*


<img width="652" height="640" alt="addtorun" src="https://github.com/user-attachments/assets/005f7250-f62f-49ec-ba4f-713b18cc4348" />

