## 📌 Overview


This README describes the various steps and commands for preprocessing the data, handling files, and running the program with input data.

📁 [Windows Subsystem for Linux (WSL)](https://ubuntu.com/desktop/wsl)


📀 [Ubuntu Server](https://ubuntu.com/download/server)


💻 [tmux Documentation](https://github.com/tmux/tmux/wiki/Getting-Started)



## 🔌 Data Preprocessing


📅 **December 22, 2024**




1. Download the TSV file  

2. Use LibreOffice Calc to process the data and save the result as an HTML file  

3. Convert newlines to spaces ([Online text tools](https://onlinetexttools.com/convert-newlines-to-spaces))

4. Save the data as List.txt 



## 🖥️ Usage - First Method


1. Clone the program and navigate to the directory
   ```bash
   git clone https://github.com/n-azimi/Bitfi.git && cd Bitfi
   ```

2. Make sure the script is executable:
   ```bash
   chmod +x script.sh
   ```

3. Run the script:
   ```bash
   ./script.sh
   ```



## 🖥️ Usage - Second Method


0. **Prerequisites**

   ```bash
   sudo apt-get install build-essential automake autoconf libtool libgmp3-dev p7zip-full tmux git
   ```

   ```bash
   git clone https://github.com/n-azimi/Bitfi.git
   ```

   ```bash
   cd Bitfi
   ```

1. **Unzipping the Password-Protected File**  

   ```bash
   7z x Bitfi.zip
   ```

2. **Running Make**  

   ```bash
   make
   ```

3. **Displaying the File Content**  

   ```bash
   cat List.txt | head -c 100
   ```

4. **Displaying the File in Hexadecimal Format**  

   ```bash
   hexdump -C List.txt | head
   ```

5. **Removing Byte Order Mark (BOM) from the File**  

   ```bash
   sed -i '1s/^\xEF\xBB\xBF//' List.txt
   ```

6. **Verifying BOM Removal** 

   ```bash
   hexdump -C List.txt | head
   ```

7. **Passing File Content as Arguments and Running the Program**

   ```bash
   chmod 777 Bitfi
   ```

   ```bash
   history -c
   ```

   ```bash
   clear
   ```

   ```bash
   xargs ./Bitfi -t 3 < List.txt
   ```

8. **Monitoring**

   ```bash
   tmux
   C-b c
   C-b 1
   top (Toggle L: Process name, Toggle d: Delay)
   exit
   ```

9. **Miscellaneous**

   ```bash
   sudo -s
   ```

   ```bash
   ls -lh
   ```

   ```bash
   command
   command &
   ```

   ```bash
   jobs
   jobs -l
   ```

   ```bash
   fg
   bg
   ```
   
   ```bash
   kill PID
   ```

   ```bash
   Ctrl + C
   ```

## ⚠️ WSL 2 Requirement

**WSL 2 must be used on Windows to avoid the `mmap: Operation not supported` error.**

In PowerShell, verify and configure WSL 2 with the following commands:

```powershell
wsl --version
wsl -l -v
wsl --update
wsl --set-version Ubuntu-24.04 2
wsl --set-default-version 2
```

