---
title: "Windows Security Fundamentals: Updates, Protection, Firewall, and Encryption"
tags:
  - study
  - exam
  - Windows
  - Cybersecurity
  - OS_Security
date: 2026-02-14T17:31:00
status: studying
format: obsidian-md
---
## Windows Updates

### Detailed Explanation

خدمة **Windows Update** هي المسؤولة عن توصيل الـ **Security updates**، والـ **Feature enhancements**، والـ **Patches** لنظام التشغيل **Windows** ومنتجات **Microsoft** التانية زي **Microsoft Defender**.

التحديثات دي بتنزل بشكل دوري ومجدول، بس لو فيه تحديث طارئ أو **Critical**، بتبعت **Microsoft** التحديث فوراً للأجهزة من غير ما تستنى الميعاد المجدول عشان تضمن حماية النظام.

> [!note]
> التحديثات مش بس للنظام، دي بتشمل كمان تحديثات الـ **Security definitions** الخاصة ببرامج الحماية المدمجة.

### Key Points Summary

- **Windows Update :** 
- بيوفر الحماية والميزات الجديدة.
- التحديثات بتنزل في يوم محدد شهرياً.
- التحديثات العاجلة (Urgent) بتنزل فوراً بغض النظر عن الجدول الزمني.

### Definitions

- **Patch Tuesday**:
دا اليوم اللي **Microsoft** بتنزل فيه التحديثات بشكل رسمي، وبيكون تاني يوم ثلاثاء من كل شهر.

### High-Risk Exam Content

- سؤال بييجي كتير عن ميعاد الـ **Patch Tuesday** (The 2nd Tuesday of each month).
- الفرق بين التحديثات المجدولة والتحديثات الـ **Urgent**.

---
## Virus & threat protection

### Detailed Explanation

دي ميزة **Built-in** جوا **Windows** هدفها حماية الجهاز من الـ **Viruses** والـ **Malware** وأي تهديدات تانية. النظام دا بيشتغل بشكل **Real-time**، يعني بيعمل **Scanning** للملفات والـ **Applications** والـ **Processes** طول ما هي شغالة عشان يلقط أي خطر في لحظتها.

الميزة دي بتسمحلك تعمل **Scans** يدوية، وتدير الملفات اللي اتعملها **Quarantine** (حجز)، وتتأكد إن الـ **Security definitions** متحدثة لآخر إصدار.

### Scan Options & Types

| Scan Type       | Description                                                                                        |
| :-------------- | :------------------------------------------------------------------------------------------------- |
| **Quick scan**  | بيفحص الفولدرات والأماكن اللي الـ **Threats** غالباً بتكون موجودة فيها في النظام.                  |
| **Full scan**   | بيفحص كل الملفات والبرامج الشغالة على الـ **Hard disk**. الفحص دا بياخد وقت طويل (ممكن يعدي ساعة). |
| **Custom scan** | بيخليك تختار ملفات أو أماكن محددة إنت عايز تفحصها بنفسك.                                           |

### Threat History Categories

1. **Last scan**: 
بيوريك تفاصيل آخر فحص **Windows Defender Antivirus** عمله بشكل أوتوماتيك.
2. **Quarantined threats**: 
دي التهديدات اللي النظام قفشها وعزلها ومنعها إنها تشتغل عشان ميحصلش ضرر للجهاز. الملفات دي بتتمسح بشكل دوري.
3. **Allowed threats**:
دي التهديدات اللي النظام صنفها كخطر، بس المستخدم سمح لها تشتغل بإرادته.

> [!warning]
> إياك تعمل **Allow** لأي **Item** متصنف كـ **Threat** إلا لو كنت متأكد 100% إنك عارف إنت بتعمل إيه، لأن دا خطر جداً.

### Protection Settings Features

- **Real-time protection**: 
بيحدد ويوقف الـ **Malware** من إنها تتسطب أو تشتغل على الجهاز.
- **Cloud-delivered protection**:
بيوفر حماية أسرع وأقوى عن طريق الوصول لبيانات الحماية الموجودة على الـ **Cloud**.
- **Automatic sample submission**:
بيبعت عينات ملفات لـ **Microsoft** عشان تساعد في حماية باقي المستخدمين من التهديدات المحتملة.
- **Controlled folder access**: 
بيحمي ملفاتك وفولدراتك ومساحات الـ **Memory** من أي تغييرات غير مصرح بيها بتعملها الـ **Unfriendly applications**.
- **Exclusions**: 
دي الحاجات اللي إنت بتقول لـ **Windows Defender** ميفحصهاش.
- **Notifications**:
إشعارات بتبلغك بحالة الجهاز والـ **Security**.

> [!warning]
> استخدام الـ **Exclusions** ممكن يخلي جهازك **Vulnerable** لأن الملفات المستبعدة دي ممكن يكون فيها **Threats**. استخدم الاوبشن دا بحذر شديد.

---
## Firewall & network protection

### Detailed Explanation

الـ **Firewall** هو اللي بيتحكم في الـ **Traffic** اللي داخل واللي خارج من الجهاز عن طريق الـ **Ports**. ممكن تتخيله كأنه "حارس أمن" واقف على الباب، بيشيك على الـ **ID** بتاع أي حاجة عايزة تدخل أو تخرج. هو اللي بيقرر مين مسموح ليه يعدي ومين لأ.

### Firewall Profiles

**Windows Firewall :** (Profiles) بيقسم الشبكات لـ 3 أنواع

1. **Domain Profile**:
    - بيتطبق لما الجهاز يكون متصل بشبكة شركة (Enterprise network) ويقدر يعمل **Authenticate** مع **Domain Controller**.

2. **Private Profile**:
    - دا **User-assigned profile**.
    - بيستخدم في الشبكات الخاصة أو المنزلية (Home networks) اللي إنت بتثق فيها.

3. **Public Profile**:
    - دا الـ **Default profile**.
    - بيستخدم في الشبكات العامة زي الـ **Wi-Fi** في الكافيهات والمطارات.
    - دا أكتر وضع فيه تشديد أمني لأن الشبكة غير موثوقة.

### Key Points Summary

- الـ **Firewall** بيتحكم في الـ Ports.
- الـ **Public Profile** هو الوضع الافتراضي والأكثر أماناً للأماكن العامة.
- الـ **Domain Profile** خاص ببيئات العمل والشركات.

### Exam-Style Questions

>[!Question] **Q1:** What is the default firewall profile for a new network connection?

>[!Answer] **Answer:** Public Profile.

>[!Question] **Q2:** Which firewall profile is used when connected to a coffee shop Wi-Fi?

>[!Answer] **Answer:** Public Profile.

---
## Bitlocker

### Detailed Explanation

- الـ **BitLocker** هي خاصية **Encryption** مدمجة في **Windows** وظيفتها تشفير الـ **Drive** بالكامل.
- الهدف منها حماية البيانات لو الكمبيوتر ضاع أو اتسرق.
- بتضمن إن أي حد غير مصرح ليه ميقدرش يوصل للملفات من غير الـ Password أو الـ PIN أو الـ Recovery Key.

عشان **BitLocker** يشتغل بأعلى كفاءة وأمان، بيحتاج شريحة (Chip) اسمها **TPM**.

### Trusted Platform Module (TPM)

- **Definition**:
شريحة أمنية صغيرة (Security chip) بتكون مدمجة في الـ Motherboard في الأجهزة الحديثة.
- **Function**: 
مسؤولة عن مهام أمنية زي تخزين الـ **Encryption keys** بشكل آمن، والتأكد من **Integrity** (سلامة) النظام قبل ما يعمل **Startup**.

### Rules / Laws / Principles

- **TPM Version Rule**:
    - **BitLocker** 
    - بيوفر أفضل حماية لما بيشتغل مع **TPM version 1.2** أو أحدث.
    - ممكن تشغيل BitLocker من غير TPM (بإعدادات خاصة)، بس وجود الـ TPM هو الأساس للحماية الكاملة.
### Key Points Summary

- **BitLocker**
- بيشفر الـ Entire drive.
- الحماية الأساسية ضد السرقة الفعلي للجهاز (Physical theft).
- بيعتمد بشكل أساسي على شريحة **TPM**.

---
# Extracted Rules & Laws

- **Patch Tuesday Rule**: 
التحديثات بتنزل في تاني ثلاثاء من كل شهر.
- **Urgent Update Rule**:
التحديثات الخطيرة بتنزل فوراً ولا تلتزم بجدول Patch Tuesday.
- **Exclusion Risk Principle**: 
استبعاد ملفات من الفحص يعني احتمالية وجود ثغرة أمنية (Vulnerability).
- **TPM Requirement**:
لتفعيل BitLocker بأقصى حماية، يجب توافر TPM v1.2 أو أحدث.

# Study Notes

- ركز جداً في الفرق بين أنواع الـ **Scans** (Quick vs Full).
- الـ **Firewall Profiles** موضع سؤال دائم، اعرف امتى تستخدم **Public** وامتى **Private**.
- **Controlled folder access**
ميزة مهمة جداً لحماية الملفات من التغييرات غير المصرح بيها.
- **System Integrity**
بيتم التأكد منها عن طريق الـ TPM عند بداية التشغيل.

# Master Summary

- **Windows Update**:
تحديثات أمنية وميزات، بتنزل في Patch Tuesday أو فوراً لو طارئة.
- **Virus & threat protection**:
حماية Real-time. أنواع الفحص: Quick, Full, Custom.
- **Quarantine**:
عزل الملفات الخطيرة.
- **Firewall**:
حارس أمن على الـ Ports. البروفايلات: Domain (شركات), Private (بيت), Public (عام/كافيهات).
- **BitLocker**:
تشفير كامل للهارد ديسك لحماية البيانات من السرقة.
- **TPM**:
شريحة أمان (Chip) بتخزن مفاتيح التشفير وبتتأكد من سلامة النظام (Hardware level security).

# Concept Connections

- **BitLocker** + **TPM**:
الاتنين مرتبطين ببعض، الـ Software (BitLocker) بيستخدم الـ Hardware (TPM) لتخزين المفاتيح.
- **Firewall** + **Ports**:
الـ Firewall هو البوابة اللي بتتحكم في الـ Ports.
- **Windows Update** + **Security Definitions**:
التحديثات هي المصدر اللي بيخلي الـ Antivirus يعرف الفيروسات الجديدة.

# Glossary

- **Patch Tuesday**: The 2nd Tuesday of each month when Microsoft releases scheduled updates.
- **Malware**: Malicious software intended to harm the device.
- **Quarantined threats**: Threats isolated by the antivirus to prevent execution.
- **Real-time protection**: Continuous scanning of files and processes as they run.
- **Firewall**: A security system controlling network traffic based on rules.
- **TPM (Trusted Platform Module)**: A hardware chip for secure cryptographic functions and system integrity checks.
- **BitLocker**: A full-disk encryption feature in Windows.
- **Controlled folder access**: A feature to protect specific folders from unauthorized changes by unfriendly apps.

---
