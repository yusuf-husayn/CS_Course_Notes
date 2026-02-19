---
title: Linux Text Editors, File Transfer, and Process Management
tags:
  - study
  - exam
  - Linux
  - CLI
date: 2026-02-08T12:17:00
status: studying
format: obsidian-md
---
## Linux Terminal Text Editors

### Detailed Explanation
في البداية، ممكن نستخدم أوامر بسيطة زي `echo` مع الـ pipe operators (`<` و `<<`) عشان نكتب جوه الـ Files. الطريقة دي شغالة تمام لو بنكتب سطر واحد أو حاجة بسيطة، لكن لو محتاجين نعدل ملفات كبيرة أو نكتب كود معقد، الطريقة دي مش هتكون عملية خالص. هنا بيجي دور الـ **Terminal Text Editors**.

الـ **Text Editors** بتخليك تقدر تفتح الملف وتعدل فيه بحرية، وتمسح وتضيف سطور براحتك. فيه أنواع كتير، لكن أشهر اتنين هما **Nano** و **VIM**.

### Nano vs VIM
#### 1. Nano
دا الـ Editor المناسب للمبتدئين. واجهته بسيطة ومباشرة جداً.
* **المميزات:** سهل الاستخدام، مش محتاج حفظ أوامر معقدة في البداية.
* **الاستخدام:** بتكتب `nano filename` وتدوس Enter، الملف بيفتح وتقدر تكتب علطول.
* **Shortcuts:** 
بتظهر تحت في الشاشة، وبتستخدم زرار `Ctrl` (اللي بيترمز له بـ `^`).
    * `Ctrl + O`: 
    عشان تعمل **Save** للتغييرات.
    * `Ctrl + X`: 
    عشان تعمل **Exit** وتقفل البرنامج.

#### 2. VIM
دا Advanced Editor وقوي جداً، بس الـ Learning curve بتاعه عالي شوية (بياخد وقت عشان تتعوده).
* **المميزات:**
    * Highly customizable (تقدر تعدل فيه براحتك).
    * بيدعم **Syntax Highlighting** (مفيد جداً للـ Developers وكتابة الكود).
    * متاح على كل الـ Terminals تقريباً (عكس Nano اللي ممكن ميكونش موجود أحياناً).
* **باختصار:** لو عايز تنجز بسرعة وأنت مبتدئ استخدم **Nano**، لو عايز Features قوية وشغل احترافي استخدم **VIM**.

> [!tip]
> الـ **Nano** هو الخيار الأسرع لو بتعدل Config file بسيط، لكن الـ **VIM** هو السلاح الأساسي لأي حد شغال System Admin أو Developer لفترات طويلة.

---
## File Transfer Methods

### Detailed Explanation
نقل الملفات مهارة أساسية في الـ Linux. سواء عايز تحمل برنامج، Script، أو صورة. فيه 3 طرق أساسية بنستخدمهم حسب الموقف: `wget`، `scp`، و `Python Web Server`.

### 1. Downloading with wget
أمر `wget` بنستخدمه لما نكون عايزين نحمل ملف من الـ Web عن طريق الـ **HTTP**. هو عامل كأنك بتعمل Download من المتصفح بس عن طريق الـ Terminal.

**Formula:**
```bash
wget [URL]
```

ببساطة بتكتب الأمر وجنبه رابط الملف، وهينزل عندك في الـ Directory اللي أنت واقف فيه.

### 2. Transferring with SCP (Secure Copy)

الـ `scp` بيستخدم لنقل الملفات بين جهازين (واحد Local وواحد Remote) بشكل آمن لأنه بيعتمد على بروتوكول **SSH** في الـ Authentication والـ Encryption.

#### Scenario A: Upload (Local to Remote)

لو عايز ترفع ملف من جهازك للـ Server.
```bash
scp [File_Name] [User]@[IP]:[Path/To/Save]
```

- **User@IP:**
بيانات الدخول للـ Remote Server.

- **Path:** .المكان اللي عايز تحفظ فيه الملف هناك

#### Scenario B: Download (Remote to Local)

لو عايز تسحب ملف من الـ Server ينزل على جهازك.
```bash
scp [User]@[IP]:[Remote_File_Path] [Local_Name]
```

> [!warning] في أمر `scp`، الترتيب مهم جداً. دايماً بنكتب **Source** الأول وبعدين **Destination**. لو عكستهم هتنقل غلط.

### 3. Serving Files with Python

لو عايز طريقة سريعة تعمل بيها Share لملفات من جهازك عشان حد تاني يسحبها، من غير ما تسطب Web Server كامل، الـ Python بتقدم حل سحري.

**Command:**
```bash
python3 -m http.server
```

- الأمر ده بيشغل **Lightweight Web Server** في الـ Directory اللي أنت واقف فيه.

- بيشتغل تلقائياً على **Port 8000**.

- أي حد معاه الـ IP بتاعك يقدر يستخدم `wget` عشان يحمل الملفات دي من عندك.

> [!note] لما تشغل الـ Python Server، الـ Terminal بيفضل مشغول (Occupied). عشان تكمل شغل لازم تفتح Terminal جديدة أو توقف الـ Server.

---
## Linux Processes

### Detailed Explanation

الـ **Process** هي أي برنامج شغال حالياً على الجهاز. الـ **Kernel** هو اللي بيدير العمليات دي. كل Process بتشتغل بتاخد رقم مميز اسمه **PID (Process ID)**. الأرقام دي بتزيد بالترتيب، يعني العملية رقم 60 بدأت بعد العملية رقم 59.

### Viewing Processes

عشان نشوف العمليات اللي شغالة، بنستخدم أدوات محددة:

1. **ps:** 
بيعرض الـ Processes الخاصة بالـ Session الحالية بس.
2. **ps aux:** 
بيعرض كل العمليات لكل الـ Users وكمان الـ System Processes (دا اللي بنستخدمه عشان نشوف الصورة كاملة).
3. **top:** 
بيعرض العمليات بشكل **Real-time** (بيتحدث كل 10 ثواني)، وبيوريك استهلاك الـ CPU والـ RAM.

### Managing Processes (Killing)

لو فيه Process مهنجة أو عايز توقفها، بتستخدم أمر `kill` مع الـ PID بتاعها.

```bash
kill [PID]
```

**Common Signals:** الأمر `kill` بيبعت إشارات (Signals) للـ Process، وأشهرهم:

- **SIGTERM:** 
إشارة بتقول للعملية "اقفلي لو سمحتي" (Terminate)، وبتديها فرصة تعمل Cleanup.

- **SIGKILL:** 
إشارة "قتل فوري" (Force Kill). مش بتدي فرصة للعملية تنظف وراها.

- **SIGSTOP:**
بتعمل Suspend أو Pause للعملية (بتجمدها) من غير ما تقفلها.

### Systemd & Child Processes

أول ما الجهاز بيعمل Boot، فيه Process أساسية بتبدأ اسمها **PID 0** وبتحمل الـ **System Initialization** (غالباً `init` أو `systemd`).

- الـ **systemd** تعتبر هي "أم العمليات".

- أي برنامج تاني بيشتغل بعدها بيكون **Child Process** منها.

- الـ systemd بتدير الـ Resources وتوزعها على الـ Child Processes.

---
## Starting & Backgrounding Processes

### Service Management (systemctl)

فيه برامج وخدمات مهمة لازم تشتغل مع بداية الجهاز (زي الـ Web Servers أو Database Servers). في الأنظمة الحديثة، بنتحكم في الخدمات دي باستخدام أداة `systemctl`.

**مثال على خدمة apache2:**

1. **Start:** `systemctl start apache2` (تشغيل الخدمة حالياً).

2. **Stop:** `systemctl stop apache2` (إيقاف الخدمة).

3. **Enable:** `systemctl enable apache2` (تشتغل أوتوماتيك مع كل Restart).

4. **Disable:** `systemctl disable apache2` (متشتغلش أوتوماتيك).

### Foreground vs. Background

أي أمر بتكتبه في الـ Terminal ممكن يشتغل في حالتين:

1. **Foreground:**
    - الوضع الطبيعي. الأمر بيشتغل وبيحجز الـ Terminal لحد ما يخلص.

    - مثال: أمر `echo` أو لما تشغل Script بياخد وقت.

    - مش هتقدر تكتب أوامر تانية لحد ما العملية دي تخلص.
    
2. **Background:**
    - العملية بتشتغل في الخلفية، والـ Terminal بيفضل متاح ليك تكتب أوامر تانية.
    
    - مفيد جداً للعمليات الطويلة (زي نسخ ملفات كبيرة).


**التحكم في الـ Background:**

- عشان تشغل أمر في الـ Background من البداية، ضيف علامة `&` في آخر الأمر.

- لو أمر شغال بالفعل في الـ Foreground وعايز توقفه مؤقتاً (Suspend)، دوس `Ctrl + Z`.

- عشان ترجع عملية من الـ Background للواجهة تاني، استخدم أمر `fg`.


> [!tip] عشان تتأكد إن العملية شغالة في الـ Background، استخدم أمر `ps aux`.

---
# Extracted Rules & Laws

- **Rule of SCP Order:** Always `Source` first, then `Destination`.

- **Rule of PID:** Each process has a unique ID managed by the Kernel, starting from boot sequence.

- **Rule of Systemd:** It is the parent process for services, handling resource allocation and boot-time starts.

# Extracted Formulas / Commands

### Text Editors
```bash
nano [filename]   # Open/Create file in Nano
vim [filename]    # Open/Create file in VIM
```

### File Transfer
```bash
wget [URL]                                      # Download file via HTTP
scp [file] [user]@[IP]:[path]                   # Upload (Local -> Remote)
scp [user]@[IP]:[file_path] [local_name]        # Download (Remote -> Local)
python3 -m http.server                          # Start HTTP server on port 8000
```

### Process Management
```bash
ps              # View current session processes
ps aux          # View all processes (users + system)
top             # Real-time monitoring
kill [PID]      # Terminate process
fg              # Bring background process to foreground
```

### Service Control
```bash
## Immediate Actions (Current Session)
systemctl start [service_name]    # Start service now
systemctl stop [service_name]     # Stops the service immediately.
systemctl restart [service_name]  # Restarts the service 
systemctl status [service_name]   # Checks the current status and recent logs.
## Boot Configuration (Startup)
systemctl enable [service_name]   # Enable auto-start on boot
systemctl enable --now [service_name] # enable a service to start
systemctl disable [service_name]  # Disables **auto-start** when the system boots.
```

# Study Notes

- **Nano vs Vim:** Nano for quick edits/beginners. Vim for power users/coding.

- **SCP Security:** `scp` is preferred over plain transfer methods because it uses SSH (Secure Shell) encryption.

- **Python Server:** Useful for quick file sharing during CTFs or hacking labs but occupies the terminal.

- **Signals:** Remember the difference between asking nicely (`SIGTERM`) and forcing (`SIGKILL`).


# Exam Notes

- **Focus Point:** Expect questions on how to transfer a file _to_ a server vs _from_ a server using `scp` (syntax order is critical).

- **Focus Point:** Differentiate between `ps` (session only) and `ps aux` (full system).

- **Focus Point:** Identify `systemd` as the first/parent process (PID 1 usually, though text mentions PID 0 concept for boot).

- **Common Trap:** Confusing `Ctrl+Z` (Suspend) with `Ctrl+C` (Kill/Terminate). `Ctrl+Z` allows you to resume later with `fg`.

# Glossary

- **Nano:** A beginner-friendly terminal text editor.

- **VIM:** An advanced, customizable terminal text editor with syntax highlighting.

- **wget:** A command-line utility for downloading files via HTTP/HTTPS.

- **SCP (Secure Copy):** A protocol for secure file transfer using SSH.

- **PID (Process ID):** A unique number assigned to each running process by the kernel.

- **Systemd:** A system and service manager for Linux, responsible for starting services at boot.

- **Signal:** A message sent to a process to request an action (e.g., terminate, stop).

- **Foreground Process:** A process that runs interactively and blocks the terminal input.

- **Background Process:** A process that runs independently, freeing up the terminal.

---
