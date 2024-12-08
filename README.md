# Dictionary Attacks - Password Cracking Analysis with Hashcat

Strictly for Academic purposes ONLY.

---

## Project Overview

This project demonstrates the process of cracking password hashes using **Hashcat** and dictionary attacks. It involves analyzing the time required to crack passwords from various hash types and sizes of dictionaries.

---

## Prerequisites

1. **Google Colab** account.
2. **Google Drive** account with sufficient storage for files and folders.
3. Installed Python packages for Jupyter Notebook execution in Colab.

---

## Setup Instructions

### Step 1: Clone the Repository
1. Clone the repository containing the provided Jupyter notebook.
2. Open the notebook in **Google Colab**.

### Step 2: Upload Password Dictionaries
1. Download the following dictionary files:
   - **[1M passwords](https://github.com/danielmiessler/SecLists/blob/master/Passwords/Common-Credentials/10-million-password-list-top-1000000.txt)**
   - **[10M passwords](https://weakpass.com/wordlists/ignis_10m.txt)**
   - **[273M passwords](https://weakpass.com/wordlists/hashkiller24.txt)**
2. Upload these files to your **Google Drive**.
3. Update the file paths in the notebook to point to the uploaded dictionary files.

### Step 3: Upload Hash Files
1. Download and upload the following hash folders to your Google Drive:
   - **Bcrypt hashes**:
     - `bcrypt1M`
     - `bcrypt10M`
     - `bcrypt273M`
   - **SHA-256 hashes**:
     - No salt:
       - `NoSalt/sha256_1M`
       - `NoSalt/sha256_10M`
       - `NoSalt/sha256_273M`
     - With salt:
       - `Salt/sha256_1M`
       - `Salt/sha256_10M`
       - `Salt/sha256_273M`
2. Update the paths in the notebook to reflect the locations of these folders.

---

## Task Instructions

### Step 1: Generate SHA-256 Hash Without Salt
1. Choose a password from the **1M Passwords dictionary**.
2. Use the `generate_sha256()` function provided in the notebook to convert the chosen password to a SHA-256 hash without salt.
3. Copy the generated hash.

### Step 2: Add Hash to the NoSalt File
1. Append the copied SHA-256 hash to the file `NoSalt/sha256_1M` in your Google Drive.

### Step 3: Crack the Password Using Hashcat
1. Run the following Hashcat command in the notebook:
   ```bash
   !hashcat -m 1400 -a 0 -O path_to_'NoSalt/sha256_1M' path_to_1M_password_dictionary

2. Replace the file paths with the correct paths to the:
  ` NoSalt/sha256_1M file`
  `1M passwords dictionary file.`

### Step 4: Analyze the Output
- Note the start and end time from the Hashcat output.
- Calculate the time difference to determine the time taken to crack the password.
Output Analysis

### Record the following observations:

- Time taken to crack the password.

### Important Notes

1. Ensure your Google Colab notebook has the necessary permissions to access files from Google Drive.
2. Use the !pip install hashcat command in the notebook to install Hashcat if not pre-installed.
3. Cracking password hashes without permission is illegal. This project is for educational purposes only.
