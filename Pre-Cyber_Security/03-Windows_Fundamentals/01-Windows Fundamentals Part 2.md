---
title: Windows Administrative Tools
tags:
  - study
  - exam
  - Windows
  - Tools
date: 2026-02-14T10:56:00
status: studying
format: obsidian-md
---
## Windows Administrative Tools

### Detailed Explanation

الصفحة دي بتتكلم عن مجموعة أدوات **Utilities** جوهرية في **Windows** بنستخدمها عشان نتحكم في النظام، نراقب أداءه، ونحل مشاكله. خلونا نمسك كل أداة ونفصص وظيفتها:

**1. System Configuration (MSConfig)**
الأداة دي معمولة مخصوص عشان الـ **Advanced troubleshooting**. أهم وظيفة ليها والسبب الرئيسي اللي بنفتحها عشانه هو تشخيص مشاكل الـ **Startup** (بداية تشغيل الجهاز). لو الجهاز بيعلق وهو بيفتح أو فيه برنامج بيعمل مشاكل مع البوت، دي أول مكان تروحله.

**2. Computer Management (compmgmt)**
دي مش مجرد أداة واحدة، دي **Console** بتجمع أدوات كتير تحت سقف واحد عشان تسهل الإدارة. بتنقسم بشكل أساسي لـ 3 أقسام رئيسية:
* **System Tools**: 
أدوات النظام.
* **Storage**:
إدارة الهارد ديسك والمساحات.
* **Services and Applications**:
التحكم في الخدمات والتطبيقات.

**3. System Information**
زي ما اسمها بيقول، وظيفتها "تجميع معلومات". الأداة دي بتديك **Comprehensive view** (نظرة شاملة وكاملة) عن كل حاجة في جهازك:
* الـ **Hardware** (الرامات، البروسيسور، إلخ).
* الـ **System components**.
* الـ **Software environment**.
بنستخدمها لما نكون عايزين نشخص مشاكل (**Diagnose computer issues**) محتاجة معلومات دقيقة عن المواصفات.

**4. Resource Monitor**
الأداة دي بتوريك "مين بيستهلك إيه" بالتفصيل الممل. بتعرض استهلاك الـ **CPU**، الـ **Memory**، الـ **Disk**، والـ **Network**.
الميزة اللي بتميزها عن الـ Task Manager العادي إنها بتعرض الاستهلاك دا:
* **Per-process**:
لكل عملية لوحدها.
* **Aggregate**: 
المجموع الكلي.
* **الأهم:** بتديك تفاصيل عن الـ **Individual file handles** والـ **Modules** اللي كل عملية ماسكاها، ودي نقطة فنية دقيقة جدًا ومهمة.

**5. Command Prompt**
دا **Application** بيخليك تتكلم مع الـ **Operating System** مباشرة عن طريق كتابة الأوامر (**Typing commands**). بنستخدمه في 3 حاجات أساسية:
* تنفيذ مهام (**Perform tasks**).
* تشغيل وظائف إدارية متقدمة (**Run advanced administrative functions**).
* حل المشاكل (**Troubleshoot issues**).

**6. Windows Registry**
دي "المخ" بتاع إعدادات الويندوز. هي عبارة عن **Central hierarchical database** (قاعدة بيانات مركزية هرمية). وظيفتها تخزن كل المعلومات الضرورية عشان نعمل **Configuration** (تهيئة) للنظام. الإعدادات دي بتخص:
* الـ **Users** (سواء واحد أو أكتر).
* الـ **Applications**.
* الـ **Hardware devices**.

> [!note]
> الـ **System Configuration** مشهورة بأمر التشغيل بتاعها **MSConfig**، والـ **Computer Management** مشهورة بـ **compmgmt**.

### Key Points Summary

- **System Configuration (MSConfig)**: 
الكلمة المفتاحية هي **Startup issues**.
- **Computer Management**: 
بتتكون من 3 أجزاء: **System Tools**, **Storage**, **Services and Applications**.
- **System Information**:
بتديك **Comprehensive view** عن الـ Hardware و Software environment.
- **Resource Monitor**:
بتراقب الـ **CPU/Memory/Disk/Network**، ومميزة بعرض الـ **File handles** والـ **Modules**.
- **Command Prompt**:
تفاعل نصي (**Typing commands**) لإدارة النظام.
- **Windows Registry**:
قاعدة بيانات هرمية (**Hierarchical database**) لتخزين الـ Configurations.

> [!tip]
> عشان تفرق في الامتحان:
> لو سألك عن "Startup" -> اختار **MSConfig**.
> لو سألك عن "Handles / Modules" -> اختار **Resource Monitor**.
> لو سألك عن "Hierarchical Database" -> اختار **Registry**.

### Definitions

- **System Configuration (MSConfig)**: Utility mainly used to diagnose startup issues.
- **Computer Management**: Utility comprising System Tools, Storage, and Services and Applications.
- **System Information**: Tool that gathers comprehensive hardware and software environment data to diagnose issues.
- **Resource Monitor**: Tool displaying per-process resource usage plus individual file handles and modules.
- **Command Prompt**: Application for interacting with the OS via commands.
- **Windows Registry**: Central hierarchical database used to store configuration info for users, apps, and hardware.

### Rules / Laws / Principles

- **Registry Structure Rule**:
    - الـ Registry لازم تكون **Central hierarchical database** (قاعدة بيانات مركزية هرمية).
    - بتخزن إعدادات لـ **Users**، **Applications**، و **Hardware devices**.

- **Computer Management Components**:
    - الأداة دي لازم تحتوي على 3 أقسام رئيسية:
    1. **System Tools**
    2. **Storage**
    3. **Services and Applications**.

### Common Mistakes / Traps

- **الخلط بين Resource Monitor و Task Manager**:
    - الـ **Resource Monitor** أدق وأعمق، خصوصًا في جزئية الـ **Handles** والـ **Modules**.

- **الخلط بين System Information و System Configuration**:
    - **System Information**: 
    لعرض المعلومات فقط (View info).
    - **System Configuration**: 
    لتغيير إعدادات الإقلاع (Manage startup).

> [!warning]
> الـ **Windows Registry** مكان حساس جدًا، أي تعديل غلط فيه ممكن يوقع النظام، عشان كدا هو بيتوصف إنه **Central database** لأي **Configuration**.

### High-Risk Exam Content

- **MSConfig & Startup**:
سؤال كلاسيكي، أي مشكلة في بداية التشغيل حلها هنا.
- **Resource Monitor Details**: 
السؤال عن الأداة اللي بتعرض **File handles** و **Modules** إجابته قولا واحدًا **Resource Monitor**.
- **Registry Definition**: 
لازم تكون عارف إنها **Hierarchical database**.

### Exam-Style Questions

>[!Question] **Q1:** Which tool would you use to view individual file handles and modules used by a specific process?
>

>[!Answer] **Answer:** 
>Resource Monitor.

>[!Question] **Q2:** You are troubleshooting a computer that crashes immediately upon startup. Which utility is best suited to diagnose this issue?

>[!Answer] **Answer:**
> System Configuration (MSConfig).

>[!Question] **Q3:** What is the central hierarchical database that stores configuration settings for hardware and applications?

>[!Answer] **Answer:** 
>Windows Registry.

---
# Extracted Rules & Laws
- **Registry Configuration Scope:** Covers Users, Applications, and Hardware devices.
- **Resource Monitor Capabilities:** Monitors CPU, Memory, Disk, Network + File Handles & Modules.

# Study Notes
- **MSConfig** = Startup Troubleshooting.
- **Resource Monitor** = Handles & Modules.
- **Registry** = Hierarchical Config Database.
- **System Info** = Comprehensive Hardware/Software View.

# Master Summary
- **MSConfig**: 
تشخيص مشاكل الـ **Startup**.
- **Computer Management**:
واجهة موحدة لـ **System Tools**, **Storage**, **Services**.
- **System Info**:
عرض مواصفات **Hardware** و **Environment**.
- **Resource Monitor**:
مراقبة الموارد وتفاصيل الـ **Handles**.
- **Command Prompt**:
تنفيذ أوامر نصية.
- **Registry**: 
قاعدة بيانات الإعدادات الهرمية.

# Glossary
- **MSConfig**: The shortcut command for System Configuration utility.
- **Hierarchical Database**: The data structure of the Windows Registry.
- **File Handle**: A system resource tracked by Resource Monitor.

---
