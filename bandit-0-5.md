# Bandit: Level 0 -> Level 5

### Level 0
* **Objective:** Log in to the Bandit server using SSH.
* **Commands:** `ssh`
* **Steps:**
  1. Connect to the server using port `2220`: ssh bandit0@bandit.labs.overthewire.org -p 2220

### Level 0 -> Level 1
* **Objective:** Find the password stored in a file named readme located in the home directory.
* **Commands:** `ls & cat`
* **Steps:**
  1. Check directory contents: ls
  2. Read the file: cat readme

### Level 1 -> Level 2
* **Objective:** Find the password stored in a file named - (dash) located in the home directory.
* **Commands:** `ls & cat`
* **Steps:**
  1. Since the filename is -, running cat - will fail because the terminal treats it as an argument. To fix this, specify the explicit path: cat ./-

### Level 2 -> Level 3
* **Objective:** Find the password stored in a file whose name contains spaces: `--spaces in this filename--`.
* **Commands:** `cat`
* **Steps:**
  1. Wrap the filename in quotes or use backslashes to escape the spaces:
      cat "./ --spaces in this filename--"
      ## OR
      cat --\ spaces\ in\ this\ filename--

## Level 3 -> Level 4
* **Objective:** Find the password stored in a hidden file within the in_here directory.
* **Commands:** cd, ls -la, cat
* **Steps:**
  1. Navigate to the directory: cd in_here
  2. Use the -la flags to list all files, including hidden ones (files starting with a dot)
  3. Read the hidden file found: `cat .hidden_file_name`
 
### Level 4 -> Level 5
* **Objective:** Find the password in the `in_here` directory, stored in the only human-readable file.
* **Commands:** `cd`, `file`, `cat`
* **Steps:**
  1. Navigate to the `in_here` directory.
  2. Check the file types of all files using the `file` command to look for ASCII text: file ./*
