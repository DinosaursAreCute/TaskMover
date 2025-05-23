# TaskMover

TaskMover is a Python-based file organization tool that allows users to define rules for organizing files in a directory. It supports features like pattern matching, file moving, unzipping, and a graphical user interface for managing rules.

## What's New in 2.1.0 (2025-05-17)

- Modularized UI logic into helper modules (e.g., ui_menu_helpers.py, ui_rule_helpers.py, etc.) for maintainability and clarity.
- Added a Theme Manager tab for full CRUD (create, read, update, delete) on custom themes.
- Removed the Colors tab; all theme management is now in the Theme Manager tab.
- Only custom themes are editable; built-in themes cannot be overwritten or modified.
- Custom themes are now included in the main theme selector in the General tab.
- Fixed all major theme application errors (e.g., no more attempts to style unsupported widgets like Menubar, Listbox, or Text via ttkbootstrap).
- Suppressed info popups for theme save/apply actions for a smoother workflow.
- Cleaned up all __pycache__ folders and checked for other unnecessary files.
- Added type hints and docstrings to all major functions in ui_settings_helpers.py and other helpers.
- Updated and clarified documentation for theme management and UI structure.
- Prevented crashes related to unsupported style keys (e.g., Menubar, Listbox, Text).
- Fixed all crashes related to theme application and widget styling.
- Fixed logic to prevent built-in theme modification.
- Fixed all references to removed Colors tab and legacy color logic.
- Broke circular imports and standardized function signatures across UI modules.
- Used PowerShell Remove-Item to clean up bytecode and __pycache__ folders.
- Improved code documentation and maintainability.
- All automated tests now pass reliably, including UI and non-UI tests.
- UI tests are automatically skipped in headless environments (e.g., CI servers).
- Theme Manager UI is fully stable and covered by automated tests.
- Fixed duplicate/hidden Add Theme button logic and improved theme manager code structure.
- Improved YAML config and theme file handling, with robust auto-fix and user prompt logic.
- Documentation and developer comments updated for clarity and maintainability.

## Features

- Define rules for organizing files based on patterns.
- Automatically move files to specified directories.
- Unzip `.zip` files into target directories.
- Enable or disable rules dynamically.
- Graphical user interface (GUI) for managing rules and configurations.
- Customizable themes and colors.
- Developer tools for testing and debugging.
- Colorful, detailed test automation and logging.

## Requirements

- Python 3.x

### Built-in Python Modules (No Installation Required)

- `os`
- `shutil`
- `fnmatch`
- `logging`
- `zipfile`
- `tkinter`

### External Python Libraries (Require Installation)


### Installing Dependencies on Windows


1. **ttkbootstrap**  
   Install with:

   ```bash
   pip install ttkbootstrap
   ```

2. **PyYAML**  
   Install with:

   ```bash
   pip install PyYAML
   ```

3. **colorlog**  
   Install with:

   ```bash
   pip install colorlog
   ```

Or simply:

```bash
pip install -r requirements.txt
```


### Installing Dependencies on Linux
For Linux users, follow the steps below based on your distribution:


#### Ubuntu/Debian
```bash
sudo apt update
sudo apt install -y python3 python3-pip
pip install -r requirements.txt
```

#### Fedora
```bash
sudo dnf install -y python3 python3-pip
pip install -r requirements.txt
```

#### Arch Linux
```bash
sudo pacman -Sy python python-pip
pip install -r requirements.txt
```

#### openSUSE
```bash
sudo zypper install -y python3 python3-pip
pip install -r requirements.txt
```

## Getting Started

1. **Clone the repository:**

   ```bash
   git clone https://github.com/yourusername/TaskMover.git
   cd TaskMover
   ```

2. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application:**

   ```powershell
   python -m taskmover
   ```

## Quick Tutorial

### 1. Launch TaskMover

Run the following command in your project directory:

```powershell
python -m taskmover
```

### 2. Set Up Your Base Directory

On first launch, you’ll be prompted to select a base directory. This is where your settings and rules will be stored.

### 3. Add a Rule

- Click the "Add Rule" button in the main window.
- Enter a name, file pattern (e.g., `*.pdf`), and destination path.
- Optionally enable unzipping and toggle the rule’s active status.
- Click "Save" to add the rule.

### 4. Organize Files

- Click the "Organize" button to move files according to your rules.
- Progress and logs will be shown in the application window.

### 5. Customize

- Change the theme or colors from the Settings menu.
- Use developer tools for testing and debugging (see Documentation).

## Documentation

For detailed documentation, refer to:

- [Changelog](./CHANGELOG.md): List of changes in each version.
- [Documentation](./DOCUMENTATION.md): Full usage and API details.
- [Requirements](./requirements.txt): List of dependencies.

## Known Bugs


see project 


## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Theme Management (v2.0+)

TaskMover now features a fully integrated Theme Manager for customizing the application's appearance. The previous Colors tab has been removed. All theme management is now handled in the Theme Manager tab within Settings.

- **Built-in themes** are available for quick selection but cannot be edited or overwritten.
- **Custom themes** can be created, edited, saved, applied, and deleted using the Theme Manager.
- Only custom themes are editable. Built-in themes are read-only.
- Custom themes appear in the main theme selector in the General tab.
- All theme changes are applied live, and only supported widgets are styled (no more errors for Menubar, Listbox, or Text styling).

### How to Use the Theme Manager

1. Open the **Settings** window from the menu.
2. Go to the **Theme Manager** tab.
3. Select a custom theme to edit, or create a new one.
4. Adjust colors for supported widgets and save your changes.
5. Apply your custom theme to see changes instantly.
6. Only custom themes can be deleted or modified.

> **Note:** The Colors tab has been removed. All color and theme customization is now centralized in the Theme Manager.
