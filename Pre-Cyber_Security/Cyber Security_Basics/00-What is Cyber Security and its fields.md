---
title: Introduction to Cybersecurity and Information Security Fundamentals
tags:
  - study
  - exam
  - cybersecurity
  - fundamentals
date: 2026-02-15T10:22:00
status: studying
format: obsidian-md
---
## Introduction to Cybersecurity

### Detailed Explanation

الـ **Cybersecurity** هو ممارسة حماية الـ **Systems** والـ **Networks** والـ **Programs** والـ **Data** من أي **Digital attacks**. الهجمات دي مش بتحصل بشكل عشوائي، دي بتكون موجهة ومخطط ليها عشان تحقق أهداف محددة للمهاجم.

الهدف الأساسي من الـ attacks دي عادة بيكون حاجة من التلاتة: الوصول للمعلومات الحساسة (Accessing sensitive information)، أو تغييرها (Changing)، أو تدميرها بالكامل (Destroying). في سيناريوهات تانية، الهدف بيكون ابتزاز المستخدمين (Extorting money) عشان يدفعوا فلوس، أو مجرد تعطيل سير العمل الطبيعي للـ Business Process.

أهمية الـ **Cybersecurity** بتيجى من إننا عايشين في عالم رقمي بالكامل (Digital world). حياتنا اليومية، الاقتصاد، وحتى الـ **Critical infrastructure** زي شبكات الكهرباء والمستشفيات، كلها معتمدة على أنظمة متصلة ببعض. أي نجاح لأي **Cyberattack** ممكن يسبب كوارث حقيقية.

تأثير الهجمات دي بيتقسم لأربع عواقب رئيسية:
1.  **Financial Loss:** 
سرقة بيانات بنكية، عملات رقمية، أو أموال مباشرة. دا غير إن تعطيل الـ Business نفسه بيسبب خساير مادية ضخمة.
2.  **Identity Theft:**
المهاجمين بيسرقوا الـ **Personal data** عشان ينتحلوا شخصيتك أو يبيعوا البيانات دي على الـ **Dark web**.
3.  **Reputation Damage:** 
بالنسبة للشركات، لو حصل **Data breach**، دا بيدمر ثقة العملاء في الشركة تمامًا.
4.  **Safety Risks:** 
ودا الأخطر، لأنه بيمس حياة الناس مباشرة لو الهجوم استهدف **Critical infrastructure** زي محطات الطاقة أو أنظمة المستشفيات.

> [!note]
> الـ Cybersecurity مش بس حماية ملفات، دا حماية للـ Infrastructure اللي حياتنا قايمة عليها.

### Key Points Summary

-   **Cybersecurity:**
حماية الأنظمة والشبكات والبيانات من الهجمات الرقمية.
-   **Attack Goals:**
الوصول للبيانات، تغييرها، تدميرها، الابتزاز المالي، أو تعطيل العمل.
-   **Consequences:**
    -   Financial Loss.
    -   Identity Theft.
    -   Reputation Damage.
    -   Safety Risks.

### Definitions

-   **Cybersecurity:** The practice of protecting systems, networks, programs, and data from digital attacks.
-   **Critical Infrastructure:** Systems that are essential for daily life, such as power grids and hospitals.
-   **Identity Theft:** Stealing personal data to impersonate a user or sell their info.

---
## Cybersecurity vs Information Security (InfoSec)

### Detailed Explanation

فيه خلط كبير بيحصل بين مصطلحين: **Cybersecurity** و **Information Security (InfoSec)**. كتير بيستخدموهم كأنهم نفس المعنى (Interchangeably)، لكن فيه فرق جوهري ودقيق بينهم.

الـ **Information Security (InfoSec)** هو المظلة الكبيرة (The broader overarching practice). هو معني بحماية المعلومة نفسها، بغض النظر عن شكلها، سواء كانت **Digital** (على كمبيوتر) أو **Physical** (ورق في ملفات). هدفه يحافظ على سرية وسلامة وتوافر المعلومة دي.

أما الـ **Cybersecurity** فهو جزء فرعي (Subset) من الـ **InfoSec**. تركيزه محدد جدًا: حماية المعلومات **Digital** فقط، والموجودة في الـ **Cyberspace**، وحمايتها تحديدًا من الـ **Cyberattacks**.

الفرق بيبان أكتر لما نقارن بينهم من حيث التركيز والتهديدات:
* **Primary Focus:**
الـ **InfoSec** بيركز على حماية البيانات نفسها (Confidentiality, Integrity, Availability). أما الـ **Cybersecurity** بيركز على حماية الـ **Digital systems** والـ **Networks** اللي بتخزن أو تعالج البيانات دي.
* **Protects Against:**
الـ **InfoSec** بيحمي من كل أنواع التهديدات (دخول غير مصرح بيه، تدمير، تعديل) سواء كان الهجوم دا إلكتروني أو حد سرق ملف ورق. الـ **Cybersecurity** بيحمي بس من التهديدات الخارجية الرقمية (External threats) زي الـ Hacking والـ Malware والـ Phishing.
* **Key Concern:**
سؤال الـ **InfoSec** هو: "هل البيانات آمنة؟" (بأي شكل كانت). سؤال الـ **Cybersecurity** هو: "هل البنية التحتية الرقمية (Hardware/Software) آمنة؟".

> [!warning]
> في الامتحان لو جالك سؤال عن حماية "الورق" أو "المعلومات الفيزيائية"، الإجابة **InfoSec** مش Cybersecurity. الـ Cybersecurity للـ Digital فقط.

### Key Points Summary

-   **InfoSec** أعم وأشمل من **Cybersecurity**.
-   **Cybersecurity** هو Subset من **InfoSec**.
-   **InfoSec Scope:** Digital + Physical.
-   **Cybersecurity Scope:** Digital only (Cyberspace).

### Exam-Style Questions

>[!Question] **Q1:** Which field is responsible for protecting physical documents from unauthorized access?

>[!Answer] **Answer:** Information Security (InfoSec).

>[!Question] **Q2:** A company wants to secure its servers against malware and phishing attacks. Which domain does this fall under?

>[!Answer] **Answer:** Cybersecurity.

---
## Cybersecurity Fields

### Detailed Explanation

مجال الـ **Cybersecurity** واسع جدًا وفيه تخصصات كتير. بشكل أساسي، بيتقسم لتلات مجالات رئيسية:

1.  **Offensive Side:**
ودا الجانب الهجومي. هنا إنت بتدور على نقاط الضعف (Weaknesses) في النظام. القاعدة هنا: "To outsmart a hacker, you need to think like one". دورك تلاقي الثغرات قبل ما المهاجم الحقيقي يلاقيها.
2.  **Defensive Side:** 
ودا الجانب الدفاعي. هنا إنت بتحمي الأنظمة (Protecting systems) وبتبني خطوط الدفاع عشان تمنع الهجمات أو تتعامل معاها لو حصلت.
3.  **Administrative Side:**
ودا الجانب الإداري، المسؤول عن وضع القوانين والـ Rules والـ Strategy للشركة. (المجال دا Out of Scope حاليًا في المحتوى دا).

### Key Points Summary

-   **Offensive Security:** Finding weaknesses (Thinking like a hacker).
-   **Defensive Security:** Protecting systems.
-   **Administrative Security:** Setting rules & strategy.

---
# Extracted Rules & Laws

* **Rule of Scope:** InfoSec covers ALL information (Digital & Physical). Cybersecurity covers ONLY Digital information.
* **Rule of Relation:** Cybersecurity is a subset of Information Security.

# Master Summary

-   **Cybersecurity** protects digital assets (systems, networks, data) from attacks aimed at theft, damage, or disruption.
-   **Impacts** of attacks include financial loss, identity theft, reputation damage, and safety risks to critical infrastructure.
-   **InfoSec (Information Security)** is the broad umbrella protecting **all forms** of data (Physical + Digital).
-   **Cybersecurity** is a specialized subset of InfoSec focusing solely on **digital threats** (Hacking, Malware, etc.).
-   **Main Fields:**
    -   **Offensive:** Finding bugs/weaknesses.
    -   **Defensive:** Building protection.
    -   **Administrative:** Governance and strategy.

# Exam Notes

-   **High-Yield Fact:** 
المفرق الرئيسي بين InfoSec و Cybersecurity هو الـ **Physical Data**. لو البيانات ورقية، دي مسؤولية InfoSec فقط.
-   **Examiner Focus:** 
التركيز دايمًا بيكون على الأهداف (Goals) بتاعة الـ Cyberattacks (Access, Change, Destroy) والعواقب بتاعتها.
-   **Pattern:**
أسئلة الـ Scenario بتيجى عشان تفرق بين الـ Offensive (الهجومي/اكتشاف الثغرات) والـ Defensive (الحماية).

# Glossary

-   **Cybersecurity:** Practice of protecting systems/networks from digital attacks.
-   **Information Security (InfoSec):** Broader practice protecting all information (digital & physical).
-   **Critical Infrastructure:** Essential assets like power grids/hospitals.
-   **Offensive Security:** Finding weaknesses and bugs in systems.
-   **Defensive Security:** Protecting systems from attacks.

---
