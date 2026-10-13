# CJGT APK Automation Project

This project contains automation scripts for testing the **CJGT (超级个体)** Android application using UI Automator XML dumps.

## Project Structure

```
cjgt-apk-kcode/
├── apk/
│   └── grl-test-2026-07-31 16_07_46.apk    # Test APK (excluded from git)
├── screenshots/
│   ├── check_page.py        # Extract text from current UI dump
│   ├── extract_text.py      # Extract text and clickable elements from UI dump
│   ├── find_coord.py        # Find coordinates for "超级个体" button
│   └── *.xml                # UI Automator XML dumps (excluded from git)
└── .gitignore
```

## Scripts Overview

### `check_page.py`
Extracts all text content from a UI Automator XML dump file.
- Reads `ui_current.xml`
- Prints all text elements with indices

### `extract_text.py`
Extracts text content and clickable element coordinates from a UI dump.
- Reads `ui_super_individual.xml`
- Prints all text elements
- Finds clickable elements with their bounds and center coordinates

### `find_coord.py`
Locates the "超级个体" (Super Individual) button coordinates.
- Searches for specific UI pattern in `ui_after_login2.xml`
- Finds the ViewGroup container and icon bounds
- Calculates center coordinates for tapping

## Usage

```bash
# Run text extraction
python screenshots/check_page.py

# Extract text and clickable elements
python screenshots/extract_text.py

# Find "超级个体" button coordinates
python screenshots/find_coord.py
```

## Requirements

- Python 3.x
- UI Automator XML dumps (generated via `adb shell uiautomator dump`)

## Note

- APK files and XML dumps are excluded from version control via `.gitignore`
- Update file paths in scripts to match your local environment before running

## License

Internal testing project