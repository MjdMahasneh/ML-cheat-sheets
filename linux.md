# Linux Commands Cheatsheet

---

## 1. File & Directory Ops

- **List:** `ls -lah`  
- **Change Dir:** `cd /path/to/dir`  
- **Make Dir:** `mkdir new_folder`  
- **Copy/Move:** `cp src dst`, `mv src dst`  
- **Remove:** `rm file`, `rm -r folder`  

**Tip:** `-h` for human-readable sizes, `-a` to show hidden files.

---

## 2. File Content

- **View:** `cat file.txt`  
- **Page through:** `less file.txt` / `more`  
- **Head/Tail:** `head -n 10 file`, `tail -n 10 file`  
- **Search:** `grep -R "pattern" .`  

**Tip:** `grep -Rni` for case-insensitive with line numbers.

---

## 3. Process Management

- **List:** `ps aux`  
- **Monitor:** `top` / `htop`  
- **Kill:** `kill PID` / `kill -9 PID`  
- **Background:** `command &` / `jobs` / `fg` / `bg`  

---

## 4. Networking

- **Check IP:** `ip addr`  
- **Ping:** `ping host`  
- **Port listening:** `netstat -tuln` / `ss -tuln`  
- **Download:** `curl -O URL` / `wget URL`  

---

## 5. Permissions & Ownership

- **Change Mode:** `chmod 755 script.sh`  
- **Change Owner:** `chown user:group file`  
- **Set SGID/Sticky Bit:** `chmod g+s dir`, `chmod +t dir`  

---

## 6. Archiving & Compression

- **Tarball:** `tar czvf archive.tar.gz folder/`  
- **Extract:** `tar xzvf archive.tar.gz`  
- **Zip:** `zip -r archive.zip folder/`  
- **Unzip:** `unzip archive.zip`  
