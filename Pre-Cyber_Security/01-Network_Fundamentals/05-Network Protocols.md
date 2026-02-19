---
title: "Network Protocols: DNS, HTTP, FTP, and Email Services"
tags:
  - study
  - exam
  - networking
  - protocols
  - ports
date: 2026-01-28T15:07:00
status: studying
format: obsidian-md
---
---
# Network Protocols & Services

## DNS (Domain Name System)

### Detailed Explanation
الـ **DNS** هو النظام اللي بيسمحلنا نستخدم أسماء مفهومة للبشر (Human-readable names) زي `example.com` بدل ما نحفظ الـ IP addresses.
هو بيشتغل بشكل أساسي على **UDP port 53** (Default)، وممكن يستخدم **TCP port 53** كـ Fallback.



عشان الـ DNS يشتغل صح، بيستخدم أنواع مختلفة من الـ **Records**:
1.  **A Record:**
ده بيربط الـ Hostname بـ **IPv4 address**.
2.  **AAAA Record:**
ده بيربط الـ Hostname بـ **IPv6 address**. (عشان تفتكرها: IPv6 أطول فمحتاج A أكتر).
3.  **CNAME Record (Canonical Name):**
ده بيعمل Mapping لـ Domain name بـ Domain name تاني (زي Alias).
4.  **MX Record (Mail Exchange):**
ده بيحدد الـ Mail Server المسؤول عن التعامل مع الإيميلات الخاصة بالـ Domain.

> [!note]
> لو عايز تعرف الـ IP بتاع أي Domain من الـ Command line، ممكن تستخدم أداة اسمها `nslookup`.

### Key Points Summary
* **الوظيفة:** تحويل الأسماء لـ IP addresses.
* **Ports:** UDP 53 / TCP 53.
* **أهم الـ Records:**
    * **A:** 
     لـ IPv4.
    * **AAAA:** 
     لـ IPv6.
    * **CNAME:**
     لعمل Alias.
    * **MX:** 
     للـ Mail Servers.

### Common Mistakes / Traps
* **الفرق بين A و AAAA:**

> [!warning]
> ركز إن **AAAA** (quad-A) مخصصة للـ **IPv6**. الـ AAAA هنا ملهاش علاقة بحجم البطاريات ولا بـ Authentication.

---
## WHOIS

### Detailed Explanation
الـ **WHOIS** عبارة عن Public Database فيها تفاصيل عن ملكية الـ Domain.
البيانات دي بتشمل اسم المسجّل (Registrant)، رقم التليفون، الإيميل، والعنوان.
أي حد يقدر يعمل Query للبيانات دي باستخدام أداة `whois` على Linux أو مواقع أونلاين [WHOIS](https://who.is/).
ممكن استخدام خدمات Privacy عشان تخفي المعلومات الشخصية دي.

### Examples
الأمر: `whois google.com` هيعرضلك بيانات زي `Creation Date` و `Expiry Date`.

---
## HTTP and HTTPS

### Detailed Explanation
**HTTP (Hypertext Transfer Protocol):**
ده أساس نقل البيانات في الـ Web، وبيشتغل على **TCP port 80**.
مشكلته إنه بيبعت البيانات **Cleartext** (غير مشفرة).

**HTTPS (HTTP Secure):**
نفس الـ HTTP بس مشفر باستخدام **SSL/TLS** وبيشتغل على **TCP port 443**.
الـ HTTPS بيضمن:
1.  **Confidentiality** (سرية).
2.  **Integrity** (سلامة البيانات).
3.  **Authenticity** (التحقق من الهوية).



> [!warning]
> الـ HTTPS لا يعني إن الموقع نفسه "Secure" أو مفيهوش Risk، هو بس بيضمن إن البيانات المنقولة بينك وبين السيرفر مشفرة.

---
## FTP (File Transfer Protocol)

### Detailed Explanation
الـ **FTP** مصمم خصيصًا لنقل الملفات (Transfer files) بكفاءة أعلى من الـ HTTP.
بيشتغل بنظام Client-Server.
بيستخدم **TCP port 21**.
بيحتاج Authentication (Username & Password).

المشكلة الكبيرة إن الـ FTP **غير آمن** (Not Secure) لأن البيانات والـ Credentials بتتبعت **Plaintext**.
البديل الآمن هو **SFTP** (SSH File Transfer Protocol).

### Key Points Summary
* **Port:** TCP 21.
* **Security:** Not Secure (Plaintext).
* **Secure Alternative:** SFTP.

---
## Email Protocols (SMTP, POP3, IMAP)

### Detailed Explanation


**1. SMTP (Simple Mail Transfer Protocol):**
ده المسؤول عن **إرسال** الإيميلات من الـ Client للـ Server أو بين الـ Servers وبعضها.
العملية شبه مكتب البريد (Post office) لما تروح تبعت طرد.
* **Port 25:** 
التقليدي (غالبًا محجوب بسبب الـ Spam).
* **Port 587:**
للـ Submission.
* **Port 465:** 
للـ SMTP over SSL.

**2. POP3 (Post Office Protocol v3):**
ده مصمم عشان **تستلم** (Retrieve) الإيميلات.
بشكل افتراضي، بيعمل **Download** للإيميل وبعدين **Delete** من السيرفر (إلا لو غيرت الـ Config).
* **Port 110:** (Default).
* **Port 995:** (Secure POP3S).

**3. IMAP (Internet Message Access Protocol):**
ده الحل لو بتستخدم أكتر من جهاز (موبايل ولابتوب) وعايز تعمل **Synchronization**.
الإيميلات بتفضل موجودة على السيرفر ومش بتتمسح بمجرد التحميل، فتقدر تشوف نفس الرسائل من أي مكان.
* **Port 143:** (Default).
* **Port 993:** (Secure IMAPS).

### Understanding Checkpoints
* **SMTP:** Send.
* **POP3:** Receive (Download & Delete).
* **IMAP:** Receive (Sync & Keep on Server).

---
# Extracted Rules & Laws

## Port Numbers Rules
* **DNS:** 53 (UDP/TCP).
* **HTTP:** 80.
* **HTTPS:** 443.
* **FTP:** 21.
* **SMTP:** 25, 587, 465.
* **POP3:** 110, 995.
* **IMAP:** 143, 993.

# Master Summary
* **DNS:**
بيحول الأسماء لـ IPs. الـ **A** لـ IPv4 والـ **AAAA** لـ IPv6.
* **HTTPS:**
بيشفر الترافيك بس مش معناه إن الموقع آمن 100%.
* **FTP:**
سريع لنقل الملفات بس بيبعت الباسورد Plaintext.
* **Email:**
    * **SMTP:** للإرسال.
    * **POP3:** للاستلام (تحميل ومسح).
    * **IMAP:** للاستلام (مزامنة وبقاء نسخة عالسيرفر).

# Exam Notes
* **High-yield fact:**
الفرق الجوهري بين POP3 و IMAP هو الـ Synchronization.
* **Trap:**
الـ AAAA Record للـ IPv6 مش للبطاريات.
* **Trap:**
الـ HTTPS بيشفر الطريق (Transit) بس مبيضمنش إن السيرفر نفسه مش خبيث.

# Glossary
* **DNS:** Domain Name System.
* **A Record:** IPv4 Address Mapping.
* **AAAA Record:** IPv6 Address Mapping.
* **MX Record:** Mail Exchange Record.
* **HTTP:** Hypertext Transfer Protocol.
* **SMTP:** Simple Mail Transfer Protocol.
* **IMAP:** Internet Message Access Protocol.

---
