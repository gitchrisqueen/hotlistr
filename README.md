# 🔄 Hot Lister (Profile Image Filter PowerShell Scripts)

This project provides a simple 2-step PowerShell-based workflow to **download profile images** from a spreadsheet and then generate a new, filtered version of the list based on which images you keep.

---

## 📦 Scripts Overview

### 1. `download-images.ps1`

> Downloads profile pictures from a `.csv` or `.xlsx` file and saves them to a folder using the associated username as the image filename.

### 2. `create-filtered-hotlist.ps1`

> Creates a new filtered spreadsheet that includes only the entries that match the profile pictures you decided to keep (based on filenames in a folder). You can also choose which data columns to include in the new file.

---

## 🛠️ Prerequisites

These scripts require PowerShell 7+ (aka PowerShell Core), which is **cross-platform**.

### ✅ Required PowerShell Modules

Install the [ImportExcel](https://www.powershellgallery.com/packages/ImportExcel) module, used for reading/writing Excel files:

```powershell
Install-Module ImportExcel -Scope CurrentUser -Force
````

---

## 💻 Installing PowerShell (if not already installed)

### macOS (via Homebrew)

```bash
brew install --cask powershell
```

Then launch PowerShell using:

```bash
pwsh
```

### Windows

Download and install PowerShell from the official site:
👉 [https://github.com/PowerShell/PowerShell/releases](https://github.com/PowerShell/PowerShell/releases)

---

## 📂 Project Setup

Clone or download the repository:

```bash
git clone https://github.com/yourusername/profile-image-filter-pipeline.git
cd profile-image-filter-pipeline
```

---

## 🚀 How to Use

### Step 1: Download Profile Pictures

Run this script inside PowerShell:

```powershell
./download-images.ps1
```

**What you'll be prompted for:**

* Spreadsheet file name (`.csv` or `.xlsx`) in the current directory
* Output folder to save downloaded profile pictures
* Column header for the image URL (default: `profile_pic_url`)
* Column header for the username (default: `username`)

📁 Each image will be saved as `username.jpg` or `username.png` based on the original image extension.

---

### Step 2: Create Filtered List

Once you manually review and delete unwanted images from the output folder, run:

```powershell
./create-filtered-hotlist.ps1
```

**You’ll be prompted for:**

* The original spreadsheet used in step 1
* The folder containing only your *kept* profile pictures
* The column header for username (default: `username`)
* Case-sensitive matching preference
* Which columns to include in the new file (you'll get a list to pick from)
* File name and output format (`.csv` or `.xlsx`)

📄 The script creates a new filtered file (like `filtered_output.xlsx`) that includes only the rows that match the images you've kept.

---

## 🧪 Example Workflow

1. **Input Spreadsheet (`users.xlsx`)**
   Contains columns like `username`, `profile_pic_url`, `email`, etc.

2. **Run `download-images.ps1`**
   Downloads all images to `profile_pics/` folder.

3. **Manually Delete Unwanted Images**
   Keep only those that match your criteria.

4. **Run `create-filtered-hotlist.ps1`**
   Outputs a new `filtered_output.xlsx` with just the users whose images remain.

---

## 🧰 Advanced Options

* Case-insensitive vs. exact match for usernames
* Custom column inclusion
* Supports both CSV and Excel inputs/outputs

---

## 📄 License

MIT License – do what you want, but give credit.

---

## 👤 Author

Built by [Christopher Queen](https://www.linkedin.com/in/christopherqueen/)
Powering automation, entrepreneurship, and transformation through code.
