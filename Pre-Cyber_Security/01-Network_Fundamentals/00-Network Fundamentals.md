---
title: "Network Fundamentals: Core Concepts, Addressing & Connectivity"
tags:
  - study
  - exam
  - Networking
  - CyberSecurity
date: 2026-01-21
status: studying
format: obsidian-md
---
---
# 1. What is a Network?

## Detailed Explanation
تخيل لو قلت لك إن عندي "Network" من المعارف، أول حاجة هتيجي في بالك إن عندي شبكة علاقات بين شخصين أو أكتر. دي نفس الفكرة بالضبط في عالم الكمبيوتر.

الـ **Network** ببساطة هي عبارة عن جهازين أو أكتر (ممكن يكونوا Computers، Printers، أو Servers) متوصلين ببعض عشان يعملوا **Share Data** (مشاركة بيانات). التوصيل ده ممكن يتم بطريقتين:
1.  **Cabled:** عن طريق كابلات مادية.
2.  **Wirelessly:** .Wi-Fiعن طريق الـ

الشبكات دي أحجامها بتختلف، ممكن تكون صغيرة جدًا زي الـ Home Network في بيتك، وممكن تكون ضخمة جدًا زي شبكات الشركات الكبيرة أو حتى الـ Internet.

## Internet Definition
الـ **Internet** بيتوصف إنه "**Network of networks**". هو البنية التحتية الضخمة اللي بتربط ملايين الشبكات ببعض حوالين العالم. هو ده اللي بيخلينا نقدر نبعت Emails، نتصفح Websites، ونتواصل. ممكن تتخيله كأنه "**Global Highway**" للبيانات.

## Key Points Summary
* الـ **Network** لازم تتكون من جهازين أو أكتر.
* الهدف الأساسي هو الـ **Data Sharing**.
* الـ **Internet** هو شبكة الشبكات اللي بتربط العالم ببعضه.

---
# 2. Device Identification (IP vs. MAC)

## Detailed Explanation
عشان الأجهزة تتواصل مع بعض وتحافظ على النظام، لازم كل جهاز يكون معروف ومحدد (Identifying and Identifiable). إيه فايدة إني أكلم حد وأنا مش عارف هو مين؟

الأجهزة في الـ Network بتتشابه مع البشر في طريقة التعريف، إحنا كبشر عندنا طريقتين عشان نتعرف:
1.  **الاسم:** وده ممكن يتغير أو يتكرر في سياقات مختلفة (بيقابله الـ **IP Address**).
2.  **بصمة الصباع:** ودي حاجة ثابتة ومميزة لكل شخص (بيقابله الـ **MAC Address**).

## Definitions
* **IP Address:** هو "الاسم" بتاع الجهاز داخل الشبكة.
* **MAC Address:** هو "البصمة" المادية للجهاز.

---
# 3. IP Address (Internet Protocol Address)

## Detailed Explanation
الـ **IP Address** هو رقم فريد (Unique Number) بيتم تعيينه لكل جهاز على الشبكة عشان نقدر نعرف مين اللي بيبعت الداتا ومين اللي بيستقبلها. هو بالضبط زي عنوان بيتك، بس للجهاز بتاعك.

فيه نوعين أساسيين من الـ IP Addresses:
1.  **IPv4:** النظام القديم والأكثر شيوعًا.
2.  **IPv6:** النظام الجديد اللي اتعمل عشان يحل مشكلة نفاذ العناوين.

## IPv4 vs. IPv6

| Feature | IPv4 | IPv6 |
| :--- | :--- | :--- |
| **Structure** | 32-bit addresses | 128-bit addresses |
| **Format** | 4 أرقام Decimal مفصول بينهم بنقط (Dots) | أرقام Hexadecimal مفصول بينهم بـ Colons (:) |
| **Example** | `192.168.1.1` | `2001:0db8:85a3::8a2e...` |
| **Capacity** | حوالي 4.3 مليار عنوان (وده مش كفاية دلوقتي) | عدد لا نهائي تقريبًا من العناوين |

> [!note]
> الـ IPv6 اتصمم عشان يستبدل الـ IPv4 لأن العناوين المتاحة في IPv4 قربت تخلص.

---
# 4. Public IP vs. Private IP

## Detailed Explanation
مش كل الـ IP Addresses زي بعض، بنقسمهم لنوعين مهمين جدًا بناءً على مكان استخدامهم:

1.  **Public IP:**
    * ده العنوان اللي بيحدد هويتك على الـ Internet.
    * اللي بيديك الرقم ده هو الـ **ISP** (Internet Service Provider).
    * ممكن الوصول ليه من أي مكان في العالم (إلا لو فيه Firewall منعه).

2.  **Private IP:**
    * ده بيستخدم *جوة* الشبكات المحلية (Local Networks) زي البيت أو الشغل.
    * مستحيل يتم الوصول ليه مباشرة من الـ Internet.
    * ليه Ranges محددة ومحفوظة ماينفعش تستخدم كـ Public IP.

## Rules: Private IP Ranges
أي IP يبدأ بالأرقام دي هو وش **Private IP**:

1.  يبدأ بـ `10` (مثلاً `10.x.x.x`).
2.  يبدأ بـ `172` (من `172.16.x.x` لحد `172.31.x.x`).
3.  يبدأ بـ `192` (تحديدًا `192.168.x.x`).

> [!warning]
> في الامتحان، لو شفت IP زي `192.168.1.77` ده فورًا Private. لو شفت `86.157.52.21` ده Public لأنه مش تبع الـ Ranges المحفوظة دي.

## Comparison Example
| Device Name | IP Address | IP Type |
| :--- | :--- | :--- |
| DESKTOP-PC | `192.168.1.77` | **Private** |
| DESKTOP-PC | `86.157.52.21` | **Public** |

---
# 5. MAC Address (Media Access Control)

## Detailed Explanation
الـ **MAC Address** هو مُعرف فريد (Unique Identifier) بيتم تعيينه للـ **Network Interface Card (NIC)**.
الفرق الجوهري بينه وبين الـ IP إن الـ MAC Address **دائم ومبيتغيرش** (Permanent)، عكس الـ IP اللي ممكن يتغير.

الـ **Switches** بتستخدم الـ MAC Address عشان تعرف أي جهاز متوصل بأي Port في الشبكة.

## Anatomy of a MAC Address
الشكل: `00:1A:2B:3C:4D:5E`
* مكتوب بنظام الـ **Hexadecimal**.
* أول جزء منه بيحدد الـ **Vendor** (الشركة المصنعة زي Intel مثلاً).
* الجزء التاني هو رقم مميز للكارت نفسه (Unique Address).

---
# 6. Connectivity Testing: Ping & ICMP

## Detailed Explanation
الـ **Ping** هي أداة (Tool) بنستخدمها عشان نختبر الـ Connectivity بين جهازين.
لما تعمل Ping، جهازك بيبعت رسالة اسمها **ICMP Message** (كأنك بتقول "أنت موجود؟").
* لو الجهاز التاني رد: يبقى فيه اتصال (Connection).
* لو ماردش: الجهاز ممكن يكون مقفول أو فيه **Firewall** بيعمل Block للرسالة دي.

## Command Usage
```bash
ping <IP Address>
# OR
ping <Website URL>
````

## Key Metrics from Ping Output

لما بتعمل Ping بيظهرلك بيانات مهمة:

- **Packet Loss:** لو 0% يبقى الاتصال ممتاز.
- **Time:** الوقت اللي خدته الرسالة عشان تروح وترجع (كل ما قل كان أحسن).
- **TTL (Time To Live):** قيمة بتحدد عمر الباكت.

---
# 7. Network Categories (Geography & Topology)

## Detailed Explanation

الشبكات بتتقسم لنوعين كبار:

1. حسب التغطية الجغرافية (**Geographical Coverage**).
2. حسب التصميم والشكل (**Topology**).


## A. Geographical Coverage Categories

1. **LAN (Local Area Network):**
- شبكة بتربط أجهزة في مساحة محدودة (مبنى، مكتب، بيت).
- بتسمح بمشاركة الـ Resources زي الطابعات والملفات والإنترنت.

1. **PAN:** (Personal Area Network) - زي البلوتوث بين موبايلك وسماعتك.
2. **MAN:** (Metropolitan Area Network) - على مستوى مدينة.
3. **WAN:** (Wide Area Network) - بتغطي مساحات ضخمة (دول وقارات).

## B. Network Topology

هي التصميم أو التخطيط المادي (Physical Layout) للشبكة. يعني إزاي الأجهزة مترتبة ومتوصلة ببعضها.

> [!tip]
> 
> ركز إن الـ LAN هي الأساس اللي بنتعامل معاه في البيوت والمكاتب، والـ Topology هي "رسمة" الشبكة على الأرض.

---
# Extracted Rules & Laws

- **Private IP Rule:** Any IP address starting with `10`, `192.168`, or the range `172.16` to `172.31` is strictly a **Private IP**.

- **MAC Address Rule:** MAC addresses are permanent physical identifiers burned into the NIC, whereas IP addresses can change logically.

- **Ping Logic:** Ping uses **ICMP** protocol. Reply = Success; No Reply = Down/Blocked.


# Extracted Formulas

- **Ping Syntax:** `ping [IP Address OR URL]`

- **Private IP Ranges:**
    - Class A Private: `10.x.x.x`
    - Class B Private: `172.16.x.x` - `172.31.x.x`
    - Class C Private: `192.168.x.x`

# Study Notes

- **Analogy to Remember:** IP Address is like your mailing address (changeable, logical). MAC Address is like your fingerprint (permanent, physical).

- **Network Hierarchy:** Internet > WAN > MAN > LAN > PAN.

- **IPv4 vs IPv6:** 32-bit (limited) vs 128-bit (unlimited).

- **Public vs Private:** Use Public to browse the internet; Use Private to share files with a printer in the same room.

# Exam Notes

- **High-Yield Question:** Identify if an IP is Public or Private based on the number.
    - _Trap:_ `172.15.x.x` is Public (because private starts at 172.16).
    - _Trap:_ `192.169.x.x` is Public (because private is 192.168).

- **Definition Check:** Make sure to distinguish between **Internet** (Infrastructure/Network of networks) and **Web** (Service).

- **Tool Usage:** Know that `ping` uses **ICMP** messages.

# Concept Connections

- **Network & IP:** A Network consists of devices; each device needs an **IP Address** to communicate.

- **IP & MAC:** To deliver data locally, the **IP Address** is used to route data to the network, but the **MAC Address** is used by the Switch to deliver it to the specific device port.

- **LAN & Private IP:** **LANs** typically utilize **Private IP** addresses to conserve Public IPs and enhance security.

# Glossary

- **Network:** Two or more devices connected to share data.
- **Internet:** The global network of networks; the infrastructure connecting millions of networks.
- **IP Address:** A unique logical identifier assigned to a device on a network (e.g., 192.168.1.1).
- **MAC Address:** A unique physical identifier assigned to a Network Interface Card (NIC) (e.g., 00:1A:...).
- **ISP:** Internet Service Provider.
- **LAN:** Local Area Network; connects devices in a limited geographical area.
- **Topology:** The physical layout or design of a network.
- **ICMP:** Internet Control Message Protocol; used by tools like ping to test connectivity.
- **IPv4:** 32-bit IP address standard.
- **IPv6:** 128-bit IP address standard.

---
