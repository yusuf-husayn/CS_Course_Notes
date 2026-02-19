---
title: Defensive Security Fundamentals & Malware Analysis
tags:
  - study
  - exam
  - cybersecurity
  - defensive_security
date: 2026-02-15T13:30:00
status: studying
format: obsidian-md
---
## Defensive Security Overview

### Detailed Explanation
الـ **Defensive Security** هي عملية حماية الـ **Computer Systems** والـ **Networks** والـ **Data** من أي **Cyberattacks** أو **Unauthorized Access**.

الموضوع مش بس إنك تستنى الهجوم يحصل، لأ، هي عبارة عن مجموعة إجراءات **Proactive** (استباقية) و **Reactive** (رد فعل) هدفها الأساسي تلات حاجات:
1. **Prevention**: .منع الهجوم قبل ما يحصل
2. **Detection**: .اكتشاف الهجوم لو حصل
3. **Response**: .التعامل مع الهجوم وتقليل ضرره

تخيل الموضوع كأنك بتبني قلعة (Fortress):
- بتبني أسوار وبوابات عشان تمنع الدخلاء (دا الـ **Prevention**).
- بتوقف حراس وأبراج مراقبة عشان تلمح أي حد بيحاول ينط من على السور (دا الـ **Detection**).
- بتجهز خطة وفريق تدخل سريع عشان لو حد دخل تمسكه وتصلح اللي بوظه (دا الـ **Response**).

### Key Points Summary
- الـ **Defensive Security** بتحمي الـ Systems والـ Networks.
- بتعتمد على **Prevention** و **Detection** و **Response**.
- الهدف هو حماية الـ Organization من الـ Threats الخارجية والداخلية.

> [!tip]
> إفتكر الـ **Defensive Security** دايما بمثال القلعة (Fortress):
> **Walls** = Prevention
> **Guards** = Detection
> **Response Team** = Response

---
## Security Operations Center (SOC)

### Detailed Explanation
الـ **SOC** هو فريق من محترفي الـ **Cybersecurity** مهمتهم الأساسية هي مراقبة الـ **Network** والـ **Systems** بشكل مستمر عشان يكتشفوا أي **Malicious Cybersecurity Events**.

الـ **SOC** بيركز بشكل أساسي على تلات حاجات:
1. **Vulnerabilities**:
لما تظهر نقطة ضعف في الـ System، لازم تتصلح بـ **Update** أو **Patch**. ولو مفيش حل متاح، لازم ياخدوا إجراءات تمنع الـ Attacker من استغلالها.
2. **Policy Violations**:
دي القواعد اللي الشركة حطاها عشان تحمي الـ Network. لو موظف رفع **Confidential Data** على موقع تخزين خارجي، دا يعتبر خرق للسياسة ولازم الـ SOC يكتشفه.
3. **Unauthorized Activity**:
زي لو حد سرق الـ **Login Credentials** (اسم المستخدم والباسورد) بتوع موظف وحاول يدخل بيهم على الشبكة. الـ SOC لازم يلقط الحركة دي ويوقفها.

### Key Points Summary
- الـ **SOC** بيعمل **Monitoring** للشبكة 24/7.
- بيتعامل مع الـ **Vulnerabilities** (الثغرات).
- بيكتشف الـ **Policy Violations** (مخالفات القواعد).
- بيوقف الـ **Unauthorized Activity** (الدخول غير المصرح بيه).

### Definitions
- **SOC (Security Operations Center)**: 
فريق مسؤول عن مراقبة وكشف الحوادث الأمنية في المؤسسة.
- **Vulnerability**: 
نقطة ضعف في النظام ممكن الـ Attacker يستغلها.

### Common Mistakes / Traps
- خطأ شائع هو اعتقاد إن الـ **SOC** هو المسؤول الوحيد عن تصليح الـ **Vulnerabilities**، لكن في الحقيقة هما بيكتشفوها ويوجهوا بضرورة حلها، مش شرط هما اللي يطبقوا الـ Patch بإيديهم.

---
## Threat Intelligence

### Detailed Explanation
الـ **Threat Intelligence** هو المعلومات اللي بتجمعها عن الأعداء المحتملين أو الحاليين.

الـ **Threat** هو أي فعل ممكن يعطل أو يضر الـ System. عشان كدا الشركات بتجمع معلومات عشان توصل لمرحلة اسمها **Threat Informed Defense**، يعني دفاع مبني على معرفة حقيقية بالخطر.

العملية دي بتمشي في خطوات:
1. **Data Collection**: 
تجميع الداتا من مصادر داخلية زي الـ **Network Logs**، أو مصادر عامة زي الـ **Forums**.
2. **Processing**:
تنظيم الداتا دي في شكل ينفع يتحلل.
3. **Analysis**:
تحليل الداتا عشان نفهم مين هما الـ **Attackers** وإيه دوافعهم.

الهدف النهائي إنك تعرف الـ **Tactics** (التكتيكات)، الـ **Techniques** (التقنيات)، والـ **Procedures** (الإجراءات) اللي العدو بيستخدمها.

### Key Points Summary
- **Threat**: .أي إجراء يضر النظام
- **Threat Intelligence**: .جمع وتحليل معلومات عن العدو للاستعداد له
- الهدف: الوصول لـ **Threat Informed Defense**.
- المراحل: **Collection** -> **Processing** -> **Analysis**.
- النتيجة: فهم الـ **Tactics, Techniques, and Procedures (TTPs)** للعدو.

> [!note]
> الـ Intelligence مش مجرد داتا خام، هي داتا تم تحليلها عشان تطلع منها بمعلومة مفيدة (Actionable Steps).

---
## Digital Forensics

### Detailed Explanation
الـ **Forensics** بشكل عام هو استخدام العلم للتحقيق في الجرائم وإثبات الحقائق. مع انتشار الكمبيوتر والـ Smartphones، ظهر الـ **Computer Forensics** اللي تطور وبقى اسمه **Digital Forensics**.

في مجال الـ **Defensive Security**، التركيز هنا بيكون على تحليل أدلة الهجوم (Evidence of an attack) ومعرفة مين الفاعل. المجالات بتشمل التحقيق في سرقة الملكية الفكرية، التجسس الإلكتروني، وحيازة محتوى غير مصرح بيه.

التحليل بيتم في منطقتين أساسيتين:
1. **File System**:
بياخدوا صورة طبق الأصل (Image) من الـ Storage عشان يحللوا البرامج المتسطبة، الملفات الموجودة، وحتى الملفات اللي اتمسحت أو اتكتب عليها جزئيًا.
2. **System Memory**:
لو الـ Attacker شغل برنامج خبيث في الـ **RAM** من غير ما يسيفه على الـ Hard Disk، هنا لازم يتاخد **Forensic Image** من الذاكرة عشان يتحلل النشاط دا.

### Key Points Summary
- **Digital Forensics**:
علم التحقيق في الجرائم الرقمية وتحليل الأدلة. بيساعد في كشف الـ **Perpetrators** (الجناة).
- **File System Analysis**:
فحص الملفات الحالية والمحذوفة على الـ Disk.
- **System Memory Analysis**:
فحص الـ RAM لكشف البرامج اللي شغالة في الذاكرة فقط.

### Definitions
- **Forensic Image**:
نسخة طبق الأصل (Low-level copy) من وسيط التخزين أو الذاكرة تستخدم للتحليل دون التعديل على الأصل.

---
## Incident Response

### Detailed Explanation
الـ **Incident** هو أي خرق للبيانات (**Data Breach**) أو هجوم سيبراني. وممكن يكون حاجة أقل خطورة زي **Misconfiguration** (إعدادات غلط)، محاولة اختراق فاشلة، أو مخالفة للسياسات.

الـ **Incident Response** هو المنهجية اللي بنمشي عليها عشان نتعامل مع الحالات دي، والهدف هو تقليل الضرر والتعافي في أسرع وقت.

المراحل الأربعة الأساسية للـ Incident Response:
1. **Preparation**:
تجهيز فريق مدرب وأدوات، ووضع إجراءات لمنع الحوادث أصلاً.
2. **Detection and Analysis**:
اكتشاف الحادثة وتحليلها لمعرفة مدى خطورتها (**Severity**).
3. **Containment, Eradication, and Recovery**:
    - **Containment**:
	محاصرة الهجوم ومنعه من الانتشار لباقي الأنظمة.
    - **Eradication**:
	إزالة سبب الهجوم (زي مسح الـ Malware).
    - **Recovery**:
	استرجاع الأنظمة للعمل بشكل طبيعي.

### Step-by-Step Process
1. **Preparation**: .كن جاهزًا قبل حدوث الكارثة
2. **Detection & Analysis**: .إعرف إن في مشكلة وإفهم حجمها
3. **Containment**: .وقف النزيف (إحصر المشكلة)
4. **Eradication**: .شيل السبب الجذري
5. **Recovery**: .رجع السيستم يشتغل تاني

> [!warning]
> أهم مرحلة هي الـ **Preparation**، لأن من غير تحضير جيد، الاستجابة للحوادث هتكون بطيئة وغير فعالة.

---
## Types of Malware

### Detailed Explanation
كلمة **Malware** هي اختصار لـ **Malicious Software**. ودا أي برنامج أو ملف مصمم عشان يضر.

أنواع الـ Malware المشهورة:
1. **Virus**:
كود بيلزق نفسه في برنامج تاني (**Attaches itself**). هدفه ينتشر من كمبيوتر للتاني، وبيشتغل عن طريق تغيير أو مسح الملفات، وممكن يخلي الجهاز بطيء جداً أو غير قابل للاستخدام.
2. **Trojan Horse**:
برنامج بيخدعك، شكله من بره مفيد (زي مشغل فيديو)، لكن جواه وظيفة خبيثة بتدي الـ Attacker تحكم كامل في جهازك.
3. **Ransomware**:
برنامج خبيث بيشفر (**Encrypts**) ملفات المستخدم، وبيخليها غير قابلة للقراءة. الـ Attacker بيطلب "فدية" (**Ransom**) عشان يديك الباسورد لفك التشفير.

### Key Points Summary
- **Virus**: .بيحتاج برنامج مضيف (Host) وبيدمر الملفات
- **Trojan**: .مخادع، يبدو بريئاً لكنه خبيث
- **Ransomware**: .بيشفر الداتا ويطلب فلوس

### Definitions
- **Malware**: 
برمجيات خبيثة تهدف للوصول غير المصرح به أو التدمير.
- **Encryption (in Ransomware)**: 
عملية تحويل البيانات لصيغة غير مفهومة لمنع المستخدم من الوصول ليها.

---
## Malware Analysis

### Detailed Explanation
الـ **Malware Analysis** هو عملية دراسة البرمجيات الخبيثة عشان نفهم تلات حاجات: بتشتغل إزاي، معمولة ليه، وإزاي نكشفها ونشيلها. المهارة دي مهمة جداً في الـ Incident Response والـ Forensics.

التحليل بيتم بطريقتين:
1. **Static Analysis**:
فحص البرنامج الخبيث من غير ما تشغله. دا بيحتاج معرفة قوية بـ **Assembly Language** (لغة الآلة) عشان تقرأ تعليمات المعالج مباشرة.
2. **Dynamic Analysis**:
تشغيل الـ Malware في بيئة معزولة ومحكمة (**Controlled Environment**) ومراقبة تصرفاته وهو شغال بيعمل إيه.

### Compare: Static vs. Dynamic Analysis

| Feature | Static Analysis | Dynamic Analysis |
| :--- | :--- | :--- |
| **Execution** | لا يتم تشغيل البرنامج | يتم تشغيل البرنامج |
| **Method** | فحص الكود والتعليمات | مراقبة السلوك والنشاط |
| **Requirement** | يحتاج معرفة بـ Assembly | يحتاج بيئة معزولة (Sandbox) |

### Exam-Style Questions
>[!Question] **Q1 :** What is the main difference between Static and Dynamic malware analysis?

>[!Answer] Answer: Static analysis inspects the malware without running it, while Dynamic analysis observes the malware's behavior while it is running.

>[!Question] **Q2 :** Which malware type encrypts user files and demands payment?

>[!Answer] Answer: Ransomware.

---
# Extracted Rules & Laws

- **Defense Principle**: Defense is both proactive (prevention) and reactive (detection and response).
- **Incident Response Rule**: The goal is to reduce damage and recover in the shortest time possible.
- **Malware Definition Rule**: Any software designed to access, change, destroy data, or extort money is considered Malware.

# Study Notes

- **SOC** deals with live monitoring and immediate threats (Vulnerabilities, Policies, Unauthorized access).
- **Threat Intel** focuses on the "Who" and "How" of the enemy (TTPs).
- **Forensics** focuses on the "Evidence" after the fact (Disk & Memory).
- **Malware Analysis** supports all the above by understanding the "Weapon" used.

# Master Summary

- **Defensive Security**: Protects systems via Prevention, Detection, and Response.
- **SOC**: Monitors networks for vulnerabilities, policy violations, and intrusions.
- **Threat Intelligence**: Collects data to understand attacker TTPs for a threat-informed defense.
- **Digital Forensics**: Analyzes File Systems and Memory to find evidence of crimes or attacks.
- **Incident Response**: 4 Phases -> Preparation, Detection/Analysis, Containment/Eradication/Recovery.
- **Malware Types**:
    - **Virus**: Attaches to programs, spreads, deletes/modifies files.
    - **Trojan**: Disguised as legitimate software, gives attacker control.
    - **Ransomware**: Encrypts files, demands ransom.
- **Malware Analysis**:
    - **Static**: Inspecting code without running (requires Assembly).
    - **Dynamic**: Running malware in a controlled environment to watch behavior.

# Exam Notes

- Examiner focus:
الفرق بين **Virus** و **Trojan** و **Ransomware**.
- Question patterns:
بيسأل كتير عن مراحل الـ **Incident Response** بالترتيب.
- High-yield facts:**Static Analysis** = No Execution; **Dynamic Analysis** = Execution.
- **SOC** responsibilities often come up as scenarios (e.g., "A user uploaded confidential data, who detects this?").

# Glossary

- **Defensive Security**: Protecting digital assets from threats.
- **SOC**: Security Operations Center.
- **TTPs**: Tactics, Techniques, and Procedures.
- **Forensics Image**: A bit-by-bit copy of storage for analysis.
- **Incident**: A security event compromising integrity, confidentiality, or availability.
- **Malware**: Malicious Software.
- **Static Analysis**: Code analysis without execution.
- **Dynamic Analysis**: Behavioral analysis during execution.

---
