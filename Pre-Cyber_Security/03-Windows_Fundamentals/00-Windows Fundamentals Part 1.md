---
title: "Windows Fundamentals: File Systems, Permissions, and System Architecture"
tags:
  - study
  - exam
  - Windows
  - Operating Systems
  - Cybersecurity
date: 2026-02-11T17:21:00
status: studying
format: obsidian-md
---
## Introduction to Windows

### Detailed Explanation
نظام التشغيل **Windows** هو الـ **Operating System (OS)** اللي طورته شركة **Microsoft**. بيعتبر واحد من أكتر الأنظمة استخدامًا في العالم سواء للـ **Personal Computers** أو الـ **Servers**.

أهم ما يميزه هو الـ **Graphical User Interface (GUI)**، ودا اللي بيخلي التعامل مع الكمبيوتر سهل عن طريق النوافذ والأيقونات والقوائم بدل ما تكتب أوامر نصية بس.

ليه لازم تتعلم **Windows** كمتخصص **Cybersecurity**؟
1.  معظم الشركات والمؤسسات بتعتمد عليه بشكل أساسي في شغلها.
2.  أساسي جداً لأي حد بيشتغل في **IT Support** أو **System Administration**.
3.  فهم الـ **Windows Internals** (خبايا النظام) شيء جوهري لو ناوي تشتغل في الـ **Pentesting** أو الـ **Red Teaming** عشان تعرف تلاقي الثغرات.

> [!note]
> الـ **Windows** بدأ من سنة 1985 وتطور لحد ما وصل للنسخ الحديثة اللي بنستخدمها دلوقتي.

### Key Points Summary
- **Windows** هو **OS** من تطوير **Microsoft**.
- يعتمد على واجهة رسومية **GUI**.
- معرفته إجبارية لمجالات **Pentesting** و **Red Teaming**.

---
## Windows Editions History

### Detailed Explanation
تاريخ **Windows** مر بمراحل كتير، وكل نسخة كان ليها دور:
- **Windows XP**: 
كان مشهور جداً وقعد فترة طويلة.
- **Windows Vista**: 
جه بعد XP بس مكنش ناجح أوي.
- **Windows 7**: 
لما **XP** انتهى دعمه، الشركات والمستشفيات نقلت لـ **Windows 7** وبقى من أنجح النسخ.
- **Windows 8 / 8.1**:
مكنوش أحسن حاجة بسبب مشاكل في التصميم والـ **Usability**.
- **Windows 10**:
جاب استقرار ودعم طويل المدى وتحسينات كبيرة.
- **Windows 11**:
تم إطلاقه في أكتوبر 2021 وهو النسخة الحالية للـ **Desktop users**.

النسخ الحديثة بتنقسم لـ **Editions**، أهمهم:
1.  **Home Edition**.
2.  **Pro Edition** (بيكون فيه مميزات أكتر للشركات والتحكم).

بالنسبة للـ **Servers**، مايكروسوفت عندها خط إنتاج اسمه **Windows Server**، وآخر نسخة هي **Windows Server 2025**.

### Key Points Summary
- **Windows 7 :**
كان الـ **Standard** لفترة طويلة في الشركات.
- **Windows 10 , 11 :**
هما الأساس حالياً.
- **Windows Server :** 
هو النسخة المخصصة لإدارة الشبكات والسيرفرات.

---
## Windows File Systems (NTFS vs FAT)

### Detailed Explanation
الـ **File System** هو "الكتاب" أو النظام اللي بيحدد إزاي البيانات بتتخزن وتترتب وتسترجع من على الـ **Hard Drive** أو الـ **SSD**.

حالياً النظام الأساسي في **Windows** هو **NTFS** (New Technology File System).

#### 1. NTFS (New Technology File System)
دا النظام الحديث والـ **Default** في الويندوز. أهم ميزة فيه إنه **Journaling File System**.
يعني إيه **Journaling**؟ يعني لو النظام وقع أو النور قطع، الـ **File System** يقدر يصلح الملفات والمجلدات التالفة أوتوماتيكياً باستخدام معلومات متسجلة في **Log File**.

**مميزات NTFS:**
- **Security & Permissions**: 
تقدر تحدد مين يفتح الملف ومين لأ.
- **Large Files**: 
بيدعم ملفات ومساحات تخزين ضخمة.
- **Encryption**: 
بيدعم تشفير الملفات.

#### 2. FAT (File Allocation Table)
دا النظام القديم وكان ليه إصدارات زي **FAT16** و **FAT32**.
- **FAT16**: 
قديم جداً، آخره مساحة تخزين 2GB.
- **FAT32**: 
تحسن شوية وبيدعم **Partitions** لحد 2TB، لكن عيبه القاتل إن أقصى مساحة للملف الواحد هي **4GB** بس.

- مش بيدعم الـ **Journaling**، يعني لو حصل خطأ البيانات ممكن تضيع بسهولة.

### Definitions
- **NTFS**: New Technology File System, supports security, huge files, and journaling.
- **Journaling File System**: A system that maintains a log to repair data in case of failure.
- **FAT32**: Older file system with a 4GB maximum file size limit.

### Key Points Summary
- **NTFS :** 
هو الـ **Standard** حالياً بسبب الأمان والـ **Reliability**.
- **FAT32 :**
مينفعش يشيل ملف واحد حجمه أكبر من **4GB**.
- **NTFS : **
بيقدر يعمل **Auto-repair** في حالة الـ **Failure**.

> [!warning]
> في الامتحانات بيركزوا جداً على عيب **FAT32** إن الـ **Max File Size** هو 4GB.

---
## NTFS Permissions

### Detailed Explanation
في نظام **NTFS**، تقدر تعمل **Access Control** دقيق جداً على الملفات والمجلدات. بتحدد هل اليوزر دا مسموح له يقرأ، يكتب، ولا يمسح.

الصلاحيات دي بتتقسم لصلاحيات على الـ **Files** وصلاحيات على الـ **Folders**:

| Permission               | Meaning for Folders                           | Meaning for Files                             |
| :----------------------- | :-------------------------------------------- | :-------------------------------------------- |
| **Full Control**         | تحكم كامل (قراءة، كتابة، حذف، تغيير صلاحيات). | تحكم كامل (قراءة، كتابة، حذف، تغيير صلاحيات). |
| **Modify**               | قراءة وكتابة وحذف الفولدر.                    | قراءة وكتابة وحذف الملف.                      |
| **Read & Execute**       | عرض الملفات وتشغيل البرامج داخل الفولدر.      | فتح الملف وتشغيله (لو برنامج).                |
| **List Folder Contents** | عرض أسماء الملفات داخل الفولدر.               | غير متاح للـ Files (N/A).                     |
| **Read**                 | فتح الفولدر ورؤية محتواه.                     | فتح الملف وقراءة محتواه.                      |
| **Write**                | إضافة ملفات جديدة جوا الفولدر.                | التعديل والكتابة جوا الملف.                   |

### Rules / Laws / Principles
- **Inheritance Principle**:
 الـ **Permissions** عادة بتتورث من الفولدر الأب (Parent Folder) للملفات اللي جواه، إلا لو غيرت دا يدوياً.

### Key Points Summary
- **Full Control :**
بتسمح بكل حاجة بما فيها تغيير الـ **Permissions** نفسها.
- **List Folder Contents :** 
خاصة بالفولدرات بس.
- **Modify :**
بتسمح بالمسح (Deletion).

---
## Windows System32 Folder

### Detailed Explanation
فولدر **System32** هو المخ والعقل المدبر لنظام الويندوز. مكانه موجود في `C:\Windows\System32`.

الفولدر دا بيحتوي على آلاف الملفات الحيوية:
1.  **DLLs (Dynamic Link Libraries)**:
مكتبات برمجية النظام والبرامج بيحتاجوها عشان يشتغلوا.
2.  **EXEs (Executables)**: 
برامج النظام الأساسية زي `cmd.exe` و `taskmgr.exe`.

لو الفولدر دا حصله أي تلف أو مسح، الويندوز مش هيشتغل (**Malfunction**). عشان كدا النظام بيحميه بـ **Permissions** قوية جداً تمنع أي حد يعدل فيه بسهولة.

### Definitions
- **System32**: The core directory containing essential Windows system files and libraries.
- **DLL**: Dynamic Link Library, shared code used by Windows applications.

> [!warning]
> "Delete System32 to make your PC faster" دي خدعة ومقلب مشهور، مسح الفولدر دا بيدمر الويندوز تماماً.

---
## User Accounts, Profiles, and Permissions

### Detailed Explanation
نظام الويندوز بيقسم المستخدمين لنوعين أساسيين (على المستوى المحلي **Local System**):

1.  **Administrator**:
    - دا "المدير". يقدر يغير في إعدادات النظام، يضيف ويمسح يوزرز، ويسطب برامج.
    - يقدر يعدل في ملفات النظام والـ **Groups**.

2.  **Standard User**:
    - دا مستخدم عادي. صلاحياته محدودة على ملفاته الشخصية بس.
    - ميقدرش يعمل **System-level changes** زي تسطيب برامج بتأثر على الجهاز كله.

كل يوزر ليه **Profile** خاص بيه بيتخزن في المسار:
`C:\Users\username`
المسار دا بيكون فيه ملفاته الشخصية وإعداداته.

الويندوز بيستخدم حاجة اسمها **ACLs (Access Control Lists)** عشان يحدد بالظبط كل يوزر مسموح له يعمل إيه (Read, Write, Execute) على كل ملف.

### Key Points Summary
- **Administrator** = System-wide access.
- **Standard User** = Personal files only.
- **Profile Path** = `C:\Users\<Name>`.
- **ACLs :** .هي القوائم اللي بتحدد الصلاحيات

---
## User Account Control (UAC)

### Detailed Explanation
الـ **UAC** هي تقنية أمان مهمة جداً هدفها تمنع التغييرات الغير مصرح بيها (**Unauthorized changes**).
هي عبارة عن "حارس" بيوقفك ويسألك: "هل أنت متأكد إنك عايز البرنامج دا يعمل تغييرات في الجهاز؟".

**إزاي بتشتغل؟**
- حتى لو أنت داخل بـ **Administrator Account**، السيستم مبيشغلش البرامج بصلاحيات كاملة طول الوقت.
- أول ما برنامج يحاول يعمل حاجة كبيرة (زي تسطيب برنامج أو تعديل ملفات نظام)، الشاشة بتضلم وتطلع رسالة الـ **UAC Prompt**.
- دا بيحمي الجهاز من الـ **Malware** اللي بيحاول يسطب نفسه في الخلفية من غير علمك.

> [!note]
> الـ **UAC** مش شغال بشكل افتراضي (by default) على الـ Built-in Administrator account، لكنه شغال لباقي الأدمنز واليوزرز.

### Key Points Summary
- **UAC :**
بيمنع الـ **Malware** من عمل تغييرات بدون إذن.
بيظهر رسالة تأكيد **Prompt** قبل تنفيذ أوامر بصلاحيات عالية.
تم تقديمه أول مرة في **Windows Vista**.

---
## Settings and Control Panel

### Detailed Explanation
في الويندوز عندنا مكانين لإدارة الإعدادات:

1.  **Control Panel**:
    - دي الواجهة التقليدية القديمة (**Legacy**).
    - موجودة من بدايات الويندوز.
    - فيها تفاصيل كتير وأدوات متقدمة للـ **System Administration**.

2.  **Settings App**:
    - دي الواجهة الحديثة (**Modern**).
    - ظهرت مع **Windows 8** و **10**.
    - مصممة تكون سهلة وتشتغل باللمس (**Touch-friendly**).

مايكروسوفت حالياً بتنقل المميزات والإعدادات تدريجياً من الـ **Control Panel** للـ **Settings App**، لكن الاتنين لسه شغالين وموجودين.

### Key Points Summary
- **Control Panel :** .للمهام المعقدة والتقليدية
- **Settings App :** .هو الواجهة الحديثة والمستقبلية

---
# Extracted Rules & Laws

- **Rule of NTFS Permissions:**
الصلاحيات بتنقسم لـ Read, Write, Modify, Full Control وتطبق على الملفات والمجلدات.
- **Rule of UAC:**
أي عملية تتطلب صلاحيات إدارية لازم تمر بـ Prompt تأكيد، حتى لو المستخدم Admin (في الحالات العادية).
- **FAT32 Limitation Law:**
أقصى حجم للملف الواحد في FAT32 هو 4GB.

# Extracted Formulas

- **Profile Path Formula:** `C:\Users\<Username>`
- **System Path Formula:** `C:\Windows\System32`

# Study Notes

- ركز جداً على الفرق بين **NTFS** و **FAT32**، خصوصاً نقطة الـ **File Size** والـ **Journaling**.
- لازم تكون عارف إن **System32** هو قلب النظام وحذفه كارثة.
- افهم الفرق بين **Administrator** و **Standard User** لأن دا أساس الـ **Privilege Escalation** في الـ Security.
- الـ **UAC** هو خط الدفاع الأول ضد التغييرات الصامتة (Silent Installations).

# Exam Notes

- **Question Pattern:** 
بيسأل كتير عن الفرق بين **Full Control** و **Modify**. (Modify بتعمل كل حاجة ما عدا تغيير الصلاحيات).
- **High-Yield Fact:**
الـ **NTFS** بيدعم الـ **Encryption** والـ **Journaling**، الـ **FAT32** لأ.
- **Examiner Focus:**
المسارات المهمة زي `System32` ومسار بروفايل اليوزر.

# Glossary

- **GUI (Graphical User Interface):** 
واجهة المستخدم الرسومية (أيقونات ونوافذ).
- **NTFS (New Technology File System):**
نظام الملفات الحديث للويندوز، يدعم الأمان واسترجاع الأخطاء.
- **FAT (File Allocation Table):**
نظام ملفات قديم ومحدود الإمكانيات.
- **Journaling:**
تقنية تسجيل التغييرات لاستعادة البيانات عند حدوث خطأ للنظام.
- **ACL (Access Control List):** 
قائمة بتحدد مين ليه صلاحية يعمل إيه على الملفات.
- **UAC (User Account Control):** 
ميزة أمان تطلب موافقة المستخدم قبل إجراء تعديلات جذرية على النظام.
- **DLL (Dynamic Link Library):** 
ملفات مكتبات مشتركة تحتوي على أكواد بيستخدمها الويندوز والبرامج.

---
