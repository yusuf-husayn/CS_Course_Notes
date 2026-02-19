 >[!Question] 00
Which command is used to display the username of the currently logged-in user?

- [ ] Whoami

- [x] whoami
>[!Reason]
>This is the standard, lowercase command specifically designed to print the effective username of the current user.

- [ ] echo whoami

- [x] echo $(whoami)
>[!Reason]
>This uses **command substitution** `$(...)`. The shell executes `whoami` first, replaces the expression with the result (the username), and then `echo` prints that result.
  
---
>[!Question] 01
Linux is not case-sensitive?

- [ ] صحيح


- [x] خطأ
>[!Reason]
>Linux is **strictly case-sensitive**. This means it distinguishes between uppercase and lowercase letters in:
>
>- **Filenames:** `File.txt`, `file.txt`, and `FILE.TXT` are treated as three completely different files.
>
>- **Commands:** `ls` is a valid command, but `LS` or `Ls` will result in a "command not found" error.
>
>- **Directories:** `Desktop` is not the same as `desktop`.

---
>[!Question] 02
Is Linux only a kernel?

- [ ] صحيح

- [x] خطأ
>[!Reason]
>While strict technical terminology defines "Linux" as just the kernel, in practical and examination contexts, a **Linux System** (often called a Distribution or Distro) is a complete **Operating System**.
>
A functional Linux OS is not _only_ a kernel; it is a combination of:
>
>1. **The Kernel:** (Hardware abstraction)
> 
>2. **GNU Utilities & Libraries:** (Basic commands like `ls`, `cp`)
> 
>3. **Shell:** (The command line interface)
>
>4. **Application Software:** (Desktop environments, servers)
>
>_The kernel alone cannot interact with the user._

---
>[!Question] 03
>If I want to search for a file called test.txt, but I am not sure about the case sensitivity (it might be Test.txt), which option should I use with the find command?

- [ ] find -name "test.txt"


- [ ] find -name test.txt

- [x] find -iname "test.txt"
>[!Reason]
>**(Best Practice):** Using quotes is the standard way to write find commands. It ensures that the shell does not try to interpret or expand the filename before passing it to the `find` command.

- [x] find -iname test.txt
>[!Reason]
>**(Works here):** Because the filename `test.txt` does not contain any special wildcard characters (like `*` or `?`), the shell passes it to the command exactly as written.


>[!tip ] If the filename had a wildcard (e.g., `test*.txt`), you **must** use quotes, or the command might fail.

---
>[!Question] 04
>If we want to search for a file called "Shatha" and we don’t know the extension of this file, which is the correct command?

- [x] find . -name "Shatha.`*`"
>[!Reason]
>- **`find .`**: Initiates the search in the current directory.
>
>- **`-name`**: Specifies that the search is based on the filename.
>
>- **`"Shatha.*"`**: This is the crucial part:
>--------------------- `Shatha`: Matches the exact base name of the file.
>---------------------`.`: Matches the dot separating the name and extension.
>---------------------`*` (Wildcard): Matches **any** sequence of characters following the dot.
>
>This pattern successfully finds files like `Shatha.txt`, `Shatha.jpg`, or `Shatha.conf`, whereas `find . -name "Shatha"` would only find a file named "Shatha" with absolutely no extension.

- [ ] locate Shatha

- [ ] grep Shatha

- [ ] find . -name "Shatha"

---
>[!Question] 05
>The & operator in Linux is used to combine multiple commands together in one line.

- [ ] صحيح

- [x] خطأ
>[!Reason]
>- **`&` (Single Ampersand):** This operator is primarily used to run a process in the **background**, allowing you to continue using the terminal while the command runs.
>
>- **To combine/chain commands:** You should use:
>--**`;` (Semicolon):** Runs commands sequentially regardless of success (e.g., `cmd1 ; cmd2`).
>-- **`&&` (Double Ampersand):** Runs the second command _only_ if the first one succeeds.

---
>[!Question] 06
>The rm command can remove both files and directories.

- [ ] صحيح

- [x] خطأ
>[!Reason]
>By default, the `rm` command removes **files only**. If you try to remove a directory using just `rm directory_name`, it will fail and show an error ("Is a directory").
>
>To remove a directory with `rm`, you **must** explicitly add the `-r` (recursive) flag (e.g., `rm -r directory_name`).

---
>[!Question] 07
>The command rm -rf / will only delete files in the current directory, not the whole system


- [ ] صحيح


- [x] خطأ
>[!Reason]
>The forward slash `/` represents the **Root Directory**, which is the very top of the Linux file system hierarchy.
>
>- **`rm -rf /`**: This command instructs the system to forcibly and recursively delete **everything** on the entire drive (system files, user data, mounted drives), effectively destroying the operating system.
>
>- **Current Directory**: To delete only the current directory, you would use `.` (dot) or `*` (asterisk), not `/`.

---
>[!Question] 08
>The root user always has UID 1 in Linux.


- [ ] صحيح

- [x] خطأ
>[!Reason]
>In Linux systems, the **root** user (superuser) is universally assigned the **User ID (UID) of 0**.
>
>- **UID 0:** Is the identifier that the kernel uses to grant unrestricted permissions.
> 
>- **UID 1:** Is typically assigned to the `daemon` user or other system service accounts, never the root user.

---
>[!Question] 09
>Which file stores user account information such as username, UID, GID, home directory, and shell?

- [ ] /etc/hosts/


- [x] /etc/passwd/
>[!Reason]
>The `/etc/passwd` file is the standard text database that stores essential login information for every user on the system. Each line in this file contains seven specific fields separated by colons:
>
>1. **Username**
>2. **Password placeholder** (usually `x`)
>3. **User ID (UID)**
>4. **Group ID (GID)**
>5. **User ID Info** (GECOS/Comment) 
>6. **Home Directory**
>7. **Command Shell**

- [ ] /etc/group/

- [ ] etc/sudoers/

---
>[!Question] 10
>Which command would you use to check open listening ports on Linux?

- [ ] ifconfog

- [ ] ping localhost

- [x] netstat -tulnp
>[!Reason]
>The `netstat` command (Network Statistics) is specifically designed to display network connections, routing tables, and interface statistics. The combination of flags used here makes it the standard tool for identifying listening ports:
>- **`-t`**: Show **TCP** ports.
>- **`-u`**: Show **UDP** ports.
>- **`-l`**: Show only **listening** sockets (ports waiting for connections).
>- **`-n`**: Show numerical addresses (don't resolve hostnames).
>- **`-p`**: Show the **PID and name** of the program listening on the port.

>[!tip] `ss -tulnp` is the modern replacement, but `netstat` is the classic correct answer here.

- [ ] traceroute

---
>[!Question] 11
>The chmod 751 file.txt gives what permissions?

- [x] Owner: rwx, Group: r-x, Others: --x
>[!Reason]
>Linux permissions use octal numbers where **Read=4, Write=2, Execute=1**.
> - **7 (Owner):** $4 + 2 + 1 = \text{Read, Write, Execute (rwx)}$
> - **5 (Group):** $4 + 0 + 1 = \text{Read, Execute (r-x)}$
> - **1 (Others):** $0 + 0 + 1 = \text{Execute only (--x)}$

- [ ]  Owner: rw-, Group: rw-, Others: r

- [ ] Owner: r--, Group: rw-, Others: --x

- [ ] Owner: rwx, Group: --x, Others: r

---
>[!Question] 12
>The . (dot) directory refers to the parent directory, while .. (double dot) refers to the current directory.

- [ ] صحيح

- [x] خطأ
>[!Reason]
>The definitions in the statement are reversed:
> - **`.` (Single Dot):** Refers to the **current** directory you are in.
> - **`..` (Double Dot):** Refers to the **parent** directory (the folder one level up).

---
>[!Question] 13
>"Imagine you are currently working in the /home/Shatha/Desktop/Ehh directory, and I want you to go back to the /home directory. Which of the following commands is correct?"

- [ ] cd ./.

- [x] cd ../..
>[!Reason]
> - **`..` (Double Dot):** Represents the parent directory (one level up).
> - **`/` (Forward Slash):** Linux uses forward slashes to separate directories.
> - **The Logic:** Combining them as `../..` moves you up **two levels** in the directory tree.

>[!tip] While the specific path in the question (`/home/Shatha/Desktop/Ehh` to `/home`) actually requires moving up _three_ levels, this is the only option that uses valid Linux syntax to move up the hierarchy. The options with backslashes (`\`) are for Windows, and single dots (`.`) keep you in the current folder.

- [ ] cd `..\..`

- [ ] cd `.\.`

---
>[!Question] 14
>If you are currently logged in as user shatha and you run the command: (su -) without specifying a username, you will switch to the root user with a full login shell if root is enabled

- [x] صحيح
>[!Reason]
> - **`su` (Switch User):** When run without a specific username, the command defaults to the **root** user.
> - **`-` (Hyphen):** This flag tells the shell to act as a **login shell**.
 >--- It completely resets the environment variables (like `HOME`, `SHELL`, `USER`, and `PATH`) to match the target user (root).
> --- It automatically changes the working directory to the target user's home directory (`/root`).
>
>_Without the hyphen (`su`), you would become root but keep your previous user's environment variables and current directory, which can cause permission issues._


- [ ] خطأ

---
