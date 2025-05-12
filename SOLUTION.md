# CASINO LFI Lab

This lab tests the student's ability to detect a classic Local File Inclusion (LFI) vulnerability on a website. By manipulating parameters in the URL, the student will gain access to sensitive files outside the visible flow of the site.

In this lab, students will learn:

- How to identify LFI-vulnerable points in a web application.
- How to manipulate relative paths to explore the file system.
- How to extract files outside the exposed directory.
- How to access sensitive information (flag) without authentication.

## Machine Specifications 🖥️

- **System:** Ubuntu Server (or Debian without GUI)
- **Web Server:** Apache + PHP
- **Site Path:** `/var/www/html/index.php`
- **Vulnerable Content:** File inclusion via GET parameter:

```php
<?php
$page = $_GET['page'] ?? 'home';
include("pages/$page.php");
?>
```

- **Pages Directory:** `/var/www/html/pages/`
    - `home.php`
    - `about.php`

- **Sensitive File:** `/var/www/html/flag.txt`

> **Note:** SSH access or privilege escalation is not required. Everything is solved from the browser.

### Machine Credentials

```bash
servername: casino-lfi-lab
username: student
password: 4geeks-lab
```

## Expected Steps for the Student

1. **Perform network reconnaissance to identify the machine.**
     - Use tools like `nmap`, `netdiscover`, or `arp-scan`.
     - Detect an IP with port **80 (HTTP)** open.

2. **Access the website from the browser.**
     - Enter the discovered IP in the browser to load the casino landing page.
     - You will see a URL like:
         ```
         http://<IP>/index.php?page=home
         ```

3. **Explore the `page` parameter in the URL.**
     - Understand that files are included from the `pages/` directory.
     - Test different values: `home`, `about`, invalid paths, etc.

4. **Manipulate the parameter to escape the subdirectory.**
     - Attempt to access:
         ```
         ?page=../../flag
         ```

5. **Read the flag directly from the browser.**
     - If done correctly, the content of `flag.txt` will be displayed.
     - The goal is to understand how an LFI vulnerability works and how to access resources outside the intended scope.
