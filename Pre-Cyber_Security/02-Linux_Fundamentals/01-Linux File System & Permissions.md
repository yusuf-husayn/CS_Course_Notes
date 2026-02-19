---
title: Linux Permissions & File System Hierarchy
tags:
  - study
  - exam
  - Linux
  - Permissions
  - FileSystem
date: 2024-02-07T16:34:00
status: studying
format: obsidian-md
---
## Linux Permissions System

### Detailed Explanation

اللينكس بيستخدم نظام **Permission system** عشان يتحكم بشكل دقيق مين يقدر يعمل **Read** أو **Write** أو **Execute** للملفات والـ **Directories**.

النظام ده بيقسم أنواع الصلاحيات لـ 3 أنواع أساسية:
1.  **Read (r):** 
ودي بتسمح إنك تشوف محتوى الـ **File**، أو تعمل **List** للملفات اللي جوه الـ **Directory**.
2.  **Write (w):**
ودي بتسمح إنك تعدل على **File**، أو تعمل **Create** و **Delete** لملفات جوه **Directory**.
3.  **Execute (x):**
ودي بتسمح إنك تشغل **File** (لو كان **Script** أو **Program**)، أو إنك تدخل وتعمل **Access** لـ **Directory**.

عشان التنظيم يكون دقيق، الصلاحيات دي بتتطبق على 3 مجموعات مختلفة:
* **Owner (u):** .ودا المستخدم اللي بيملك الملف
* **Group (g):**
ودول المستخدمين اللي أعضاء في نفس الـ **Group** الخاصة بالملف.
* **Others (o):**
ودول أي حد تاني غير الـ Owner والـ Group (أي حد تاني).

> [!note]
> الـ Permissions في اللينكس مرنة جدًا (**Flexible**). يعني حتى لو الملف ليه **Owner** محدد، تقدر تدي **Group** كامل صلاحيات خاصة على نفس الملف من غير ما تغير صلاحيات الـ **Owner** نفسه.

### Key Points Summary

- **Read (r):** View content / List files.
- **Write (w):** Modify file / Create & Delete inside directory.
- **Execute (x):** Run program / Access directory.
- **Owner (u):** The user who owns the file.
- **Group (g):** Users in the file's group.
- **Others (o):** Everyone else.

### Examples

**مثال على استخدام الـ Groups في الـ Web Server:**
لو عندك **Web server user**، هو محتاج صلاحيات **Read** و **Write** عشان الموقع يشتغل. في نفس الوقت، شركة الاستضافة (**Hosting company**) مش هينفع تدي العملاء بتوعها صلاحية استخدام الـ Account بتاع الـ Web server مباشرة لأن دا يعتبر **Security risk** كبير.

الحل هنا باستخدام الـ **Linux permissions**: الشركة بتعمل **Group** وتدي للعملاء صلاحية إنهم يرفعوا ويديروا ملفاتهم الخاصة من غير ما ياخدوا نفس الـ **Access** بتاع الـ Web server user.

### Understanding Checkpoints

- **Define** the 3 types of Linux permissions.
- **Explain** the difference between Owner, Group, and Others.
- **Why** is giving direct account access a security risk?

---
## Linux Common Directories

### Detailed Explanation

الـ **Filesystem** في اللينكس ليه هيكل ثابت ومنظم، وكل **Directory** ليه وظيفة محددة. الترتيب بيبدأ من الـ **Root directory** اللي الرمز بتاعه `/` وده قمة الهرم في الـ Filesystem.

تحت الـ Root في مجموعة **Directories** أساسية:
1.  **/bin:** 
ودا فيه الـ **Essential binaries**، يعني الأوامر الأساسية اللي أي يوزر ممكن يحتاجها زي `ls`, `cp`, `cat`.
2.  **/sbin:** 
دا خاص بالـ **System binaries**، ودي أدوات للـ **Admin tasks** بس، زي أوامر `shutdown` و `mount`.
3.  **/etc:**
المكان دا فيه الـ **Configuration files**، ودي إعدادات الـ System بالكامل (**System-wide settings**).
4.  **/home:**
دا اللي بيكون فيه الـ **Home directories** لليوزرز العاديين (مثلًا `/home/shatha`).
5.  **/root:** 
خد بالك دا مش الـ Root directory (`/`)، دا الـ **Home directory** الخاص بالـ **Root user** نفسه.
6.  **/var:**
مخصص للـ **Variable data**، يعني البيانات اللي بتتغير كتير زي الـ **Logs**، الـ **Caches**، والـ **Spool files**.
7.  **/tmp:**
مخصص للـ **Temporary files**، والملفات اللي هنا بتتمسح أوتوماتيك لما تعمل **Reboot**.
8.  **/usr:**
بيحتوي على الـ **User programs** والـ **Libraries** والـ **Documentation**.
9.  **/opt:**
مخصص للـ **Optional software**، وعادة بيكون لبرامج الـ **Third-party apps**.

### Key Points Summary

- **/**: Top of the filesystem.
- **/bin:** Basic commands (Essential binaries).
- **/sbin:** Admin commands (System binaries).
- **/etc:** Config files.
- **/home:** Users' personal directories.
- **/root:** Root user's home.
- **/var:** Logs and variable data.
- **/tmp:** Temp files (cleaned on reboot).

### Common Mistakes / Traps

- **الخلط بين `/` و `root/`:**
    - الـ `/` هو بداية النظام كله (The Root Directory).
    - الـ `root/` هو مجرد فولدر شخصي (Home) لليوزر اللي اسمه root.

> [!warning]
> الـ Files الموجودة في `tmp/` بتتحذف تلقائيًا بمجرد ما تعمل **Reboot** للنظام، فمتحطش فيها حاجة مهمة دايمة.

### Exam-Style Questions

>[!Question] **Q1: What is the difference between `/bin` and `/sbin`?**

>[!Note] **Answer:**
`/bin` contains essential binaries for basic commands like `ls` and `cp` usable by all users, while `/sbin` contains system binaries for admin tasks like `shutdown` and `mount`.

>[!Question] **Q2: Which directory stores system-wide configuration files?**

>[!Note] **Answer:**
The `/etc` directory.

>[!Question] **Q3: Who does the permission group "Others" refer to?**

>[!Note] **Answer:**
It refers to everyone else who is not the Owner and not a member of the Group.

---
# Extracted Rules & Laws

- **Permission Hierarchy:** Permissions are assigned to Owner (u) first, then Group (g), then Others (o).
- **Reboot Cleaning Rule:** Files in `/tmp` are automatically cleaned upon system reboot.

# Study Notes

- الـ **Permissions** هي أساس الـ Security في اللينكس (Control who can r/w/x).
- الـ **Groups** معمولة عشان الـ Flexibility في إدارة الصلاحيات لمجموعة يوزرز من غير ما نعتمد على الـ Owner بس.
- لازم تحفظ وظيفة كل **Directory** لأنها ثابتة في كل أنظمة اللينكس.

# Master Summary

- **Linux Permissions:**
    - Types: Read (r), Write (w), Execute (x).
    - Scopes: Owner (u), Group (g), Others (o).
- **FileSystem Structure:**
    - `/`: Root of filesystem.
    - `/bin`: Basic binaries.
    - `/sbin`: Admin binaries.
    - `/etc`: Configs.
    - `/home`: User homes.
    - `/var`: Logs/Variable data.
    - `/tmp`: Temporary files.
    - `/opt`: Third-party software.

# Glossary
- **Permission:**
التحكم في مين يقدر يقرأ أو يكتب أو يشغل ملف.
- **Owner (u):** .المستخدم اللي أنشأ أو يمتلك الملف
- **Group (g):** .مجموعة مستخدمين ليهم صلاحيات مشتركة على ملف
- **Binaries:** .ملفات تنفيذية (أوامر وبرامج)
- **Configuration Files:** .ملفات الإعدادات الخاصة بالنظام

---
