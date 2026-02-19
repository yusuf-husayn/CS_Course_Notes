---
title: Network Topologies, Devices, and Core Protocols
tags:
  - study
  - exam
  - networking
  - topologies
  - devices
  - protocols
date: 2026-01-22T13:20:00
status: studying
format: obsidian-md
---
---
# Network Topologies

## Detailed Explanation

الـ **Topology** هو التصميم أو الشكل الهندسي للـ Network، يعني إزاي الـ Devices بتترتب وتتوصل ببعضها. عندنا 3 أنواع أساسية لازم نكون عارفينهم كويس:

**1. Star Topology**
ده النوع الأكثر شيوعًا واستخدامًا. هنا كل الـ Devices بتتوصل بجهاز مركزي واحد (ممكن يكون Switch أو Hub).

- **المميزات:** سهل جدًا إننا نوسع الشبكة (Expand)، ولو حصل عطل في كابل واحد، العطل ده بيبقى Isolated (معزول) ومش بيأثر على باقي الشبكة.

- **العيوب:** لو الجهاز المركزي (Central device) ده باظ، الـ Network كلها بتقع وتقف تمامًا.


**2. Ring Topology** 
في النوع ده، كل Device بيتوصل بالجهاز اللي بعده لحد ما يعملوا حلقة مغلقة (Closed Loop). الـ Data بتمشي في اتجاه واحد أو اتجاهين.

- **المميزات:** الأداء بيكون ثابت ومستقر (Consistent performance) حتى لو الحمل (Load) متوسط.

- **العيوب:** لو حصل قطع واحد بس في الـ Loop دي، الـ Network كلها بتقع (إلا لو كانت Bidirectional يعني البيانات بتمشي في الاتجاهين).


**3. Bus Topology**
هنا كل الـ Devices بتتوصل بكابل رئيسي واحد بنسميه الـ **Backbone**.

- **المميزات:** سهل جدًا في تركيبه (Setup) وتكلفته قليلة (Low cost).

- **العيوب:** لو الـ Backbone الرئيسي ده حصله حاجة، الـ Network كلها بتقع. وكمان الـ Performance بيقل كل ما عدد الـ Devices يزيد.


## Key Points Summary

- **Star Topology:** 
- بتعتمد على Central Device. لو وقع، الكل يقع. سهلة في التوسع.
- **Ring Topology:** 
- حلقة مغلقة. القطع فيها بيموّت الشبكة.
- **Bus Topology:** 
- كابل واحد Backbone. رخيص بس لو الكابل اتقطع الشبكة انتهت، والأداء بيقل مع الزحمة.

> [!tip]
> 
> الـ Star Topology هو الـ Standard دلوقتي في معظم الأماكن عشان لو جهاز واحد باظ، الباقي شغال عادي.

## Definitions
- **Topology:** The design or physical layout of a network, describing how devices are arranged and connected.

- **Backbone:** The main cable in a Bus Topology that connects all devices.

---
# Network Devices

## Detailed Explanation

هنتكلم عن جهازين أساسيين في أي Network: الـ **Switch** والـ **Router**.

**1. Switch** 
الـ Switch هو جهاز مخصص جوه الـ Network وظيفته يجمع (Aggregate) كذا جهاز مع بعض زي الكمبيوترات والـ Printers باستخدام كابلات Ethernet.

- الأجهزة بتتوصل في فتحات الـ Switch اللي بنسميها **Ports**. الـ Switches بتيجي بأعداد Ports مختلفة (4, 8, 16, 24, 32, 64) عشان تستوعب عدد أجهزة كبير.

- بيستخدم عادة في الشبكات الكبيرة زي الشركات والمدارس.

- **ليه هو ذكي؟** الـ Switch أكفأ بكتير من الـ Hubs أو الـ Repeaters القديمة. ليه؟ لأنه بيعرف ومتابع (Keeps track) كل جهاز متوصل بـ Port رقم كام.

- لما بيستقبل **Packet**، مش بيبعتها لكل الناس وخلاص (زي الـ Hub)، لأ ده بيبعتها بس للـ Target المقصود. ده بيقلل الـ Network Traffic جدًا وبيخلي الشبكة سريعة.

**2. Router**
الـ Router وظيفته إنه يربط الـ Networks ببعضها وينقل الـ Data بينهم.

- بيعمل عملية اسمها **Routing** (وعشان كده اسمه Router).
- الـ Routing هو عملية نقل الـ Data عبر الشبكات، يعني بيخلق مسار (Path) عشان الـ Data توصل بسلام.
- الـ Switches والـ Routers ممكن يتوصلوا ببعض عادي جدًا في الشبكة.

## Key Points Summary

- **Switch:
-  بيربط الأجهزة في نفس الشبكة (LAN). ذكي، بيبعت الـ Packet للجهاز المعين بس.
- **Router:** 
- بيربط شبكات مختلفة ببعض (Connects Networks). بيحدد المسار (Routing).


> [!note]
> 
> الفرق الجوهري: الـ Switch بيربط Devices عشان يعمل Network، لكن الـ Router بيربط Networks ببعضها.

### Definitions

- **Switch:** A dedicated device designed to aggregate multiple devices on a network using ethernet.
- **Router:** A device used to connect networks and pass data between them using routing.
- **Routing:** The process of data travelling across networks by creating a path for delivery.


---
# Subnetting

## Detailed Explanation

الـ **Subnetting** هو مصطلح معناه إننا نقسم الـ Network الكبيرة لشبكات أصغر ومصغرة (Miniature networks) جوه نفسها. تخيل شركة كبيرة، بدل ما كلهم يبقوا في شبكة واحدة سايحة على بعض، بنقسمهم لإدارات مختلفة زي: Accounting, Finance, Human Resources.

مثال عملي:

لو عندنا Network عنوانها `192.168.1.0/24`. ممكن نقسمها لجزئين:

1. `192.168.1.0/25`
2. `192.168.1.128/25`

إحنا بنعمل كده ليه؟ عشان 3 فوايد أساسية:

1. **Efficiency:** .كفاءة أعلى في الشبكة
2. **Security:** .أمان أكتر (فصل الإدارات عن بعض)
3. **Full control:** .تحكم كامل في إدارة الشبكة

## حساب الـ Subnet Mask
### Method 1: From CIDR to Decimal
**Detailed Explanation**
دي الطريقة الأساسية اللي بنحول فيها الـ **CIDR Notation** (زي `/24`) للشكل العشري المألوف (Dotted Decimal Format). الفكرة كلها إن الرقم اللي بعد الـ Slash `/` بيعبر عن عدد الـ **Ones (1s)** في الـ Mask.

**Step-by-Step Process**
1. **Identify CIDR:**
شوف الرقم اللي بعد `/` (مثلاً `/24`).
2. **Write Binary:** 
اكتب عدد وحايد (1s) يساوي الرقم ده، وكمل الباقي أصفار (0s) لحد ما تقفل 32 bit.

3. **Split Octets:**
قسم الـ 32 bit لأربع مجموعات، كل مجموعة 8 bits.
4. **Convert to Decimal:** 
حول كل Octet من Binary لـ Decimal.

>[!Examples]
>**Example 1: /24**
>- **Bits:**
>عندنا 24 bit قيمتهم `1`.
>
>- **Binary:** 
>`11111111.11111111.11111111.00000000`
>
>- **Conversion:**
>
>    - `11111111` = 255
>    - `00000000` = 0
> 
>- **Result:** `255.255.255.0`
>---
>**Example 2: /26**
>- **Bits:**
>
>عندنا 26 bit قيمتهم `1`، والباقي أصفار.
>- **Binary:**
>`11111111.11111111.11111111.11000000`
>
>- **Conversion:**
>   - أول 3 Octets زي بعض (255).
>   - الرابع: `11000000` = (128 + 64) = 192.
>- **Result:** `255.255.255.192`


### Method 2: Calculation Based on Host Requirements
**Detailed Explanation**
الطريقة دي بنستخدمها لما نكون محتاجين عدد معين من الأجهزة (Hosts) وعايزين نعرف الـ **Subnet Mask** المناسب اللي يغطي العدد ده.

**Formulas**
$$2^n - 2 \geq \text{Required Hosts}$$

- **$n$**:
عدد الـ Bits الخاصة بالـ Host (اللي قيمتها 0).
**$-2$**: بنطرح عنوانين (واحد للـ Network Address وواحد للـ Broadcast Address).

**Step-by-Step Process**
1. **Determine Hosts:** 
حدد عدد الأجهزة المطلوب (مثلاً 50 جهاز).

2. **Calculate n:**
جرب قوى العدد 2 ($2^n$) لحد ما تلاقي رقم أكبر من أو يساوي (المطلوب + 2).

3. **Find Network Bits:**
اطرح عدد الـ Host bits من 32.
- $\text{Network Bits} = 32 - n$

3. **Write CIDR:**
الناتج هو الـ CIDR بتاعك (مثلاً `/26`).

4. **Convert:**
حول الـ CIDR لـ Decimal بالطريقة الأولى.

>[!tip] Examples
>**Scenario: Need 50 Hosts**
>
>1. **Try powers of 2:**
>  - $2^5 = 32$ (مش كفاية).
>  - $2^6 = 64$.
>2. **Check Formula:** $64 - 2 = 62$ host. (الـ 62 تغطي الـ 50 مستريح).
> 
>3. **Identify Bits:**
>    - Host bits ($n$) = 6.
>    - Network bits = $32 - 6 = 26$.
>4. **Result:**
>    - CIDR: `/26`
>    - Subnet Mask: `255.255.255.192`

### Method 3: Quick Calculation (Bit Values)
**Detailed Explanation**
دي طريقة سريعة للمحترفين بتعتمد على حفظ قيم الـ Bits في الـ Octet الواحد. بدل ما نكتب وحايد وأصفار كتير، بنجمع القيم المقابلة للـ Ones في الـ Octet الأخير.

**Rules / Laws / Principles**
قيم الـ Bits من الشمال لليمين في أي Octet:

| **Bit Position** | **1**   | **2**  | **3**  | **4**  | **5** | **6** | **7** | **8** |
| ---------------- | ------- | ------ | ------ | ------ | ----- | ----- | ----- | ----- |
| **Value**        | **128** | **64** | **32** | **16** | **8** | **4** | **2** | **1** |
> [!tip] عشان تحسب الـ Mask بسرعة: إجمع الأرقام اللي تحتها "1" في الـ Binary. مثال: لو عندك 3 وحايد (11100000) $\rightarrow$ إجمع $128 + 64 + 32 = 224$

> [!tip] Examples
> **Scenario: Borrowing 3 bits for Network**
> - عندنا 3 وحايد في الـ Octet الأخير  
>   `11100000`
> - Calculation  
>   128 + 64 + 32 = 224
> - Result  
>   255.255.255.224

> [!warning] **Common Pitfalls:**
> - **Forgetting -2:** 
>نسيان طرح 2 من المعادلة، وده ممكن يخليك تختار Mask مش مكفي الأجهزة (خاصة لو العدد المطلوب قريب من الحد الأقصى).
>
>- **Confusion:**
>الخلط بين عدد الـ Subnets (اللي بيعتمد على Network bits) وعدد الـ Hosts (اللي بيعتمد على Host bits).
>
>- **Memorization:**
>حفظ الأرقام زي 192 و 224 من غير فهم أصلها (مجموع الـ Bit Values)، وده بيخليك تغلط لو نسيت.
## Definitions
- **Subnetting:** Splitting up a network into smaller, miniature networks within itself.

## Key Points Summary

- **الهدف:** تقسيم الشبكة الكبيرة لأجزاء صغيرة.
- **الفائدة:** .Efficiency, Security, Control

---
# Core Network Protocols

## 1) ARP (Address Resolution Protocol)

### Detailed Explanation

الـ **ARP** هو Protocol بيشتغل جوه الـ Local Network (LAN). وظيفته الأساسية هي الربط أو الـ Mapping بين حاجتين:

1. الـ **IP Address**.
2. الـ **MAC Address**.

### Step-by-Step Process

إزاي الـ ARP بيشتغل؟

1. جهازك عايز يكلم جهاز تاني ومش معاه الـ MAC بتاعه، فبيعمل **Broadcast** (ينادي بأعلى صوته في الشبكة): "يا جماعة، مين اللي عنده الـ IP رقم X.X.X.X؟".
2. الجهاز صاحب الـ IP ده (Target Device) بيرد عليه ويقوله: "أنا أهو، وده الـ MAC Address بتاعي".
3. الجهاز اللي سأل بياخد المعلومة دي ويخزنها عنده في حاجة اسمها **ARP Cache** عشان يستخدمها بعد كده من غير ما يسأل تاني.

### Definitions

- **ARP:** A protocol that maps an IP address to a MAC address inside a local network.

> [!tip]
> 
> إفتكرها دايماً: ARP هو اللي بيجيب الـ "Fingerprint" (MAC) لما يكون معاك الـ "Name" (IP).

---
## 2) DHCP (Dynamic Host Configuration Protocol)

### Detailed Explanation

الـ **DHCP** هو المسؤول عن توزيع الـ IP Addresses للأجهزة في الشبكة.

الـ IP ممكن ندخله للجهاز بطريقتين:

1. **Manually:** 
نكتبه بإيدنا (Physically entering them).
2. **Automatically:** 
 وده الشائع، عن طريق **DHCP Server**.

لما جهاز جديد يدخل الشبكة ومش معاه IP، بتحصل عملية تفاوض عشان ياخد IP، الخطوات دي بنسميها عملية الـ DORA (مأخوذة من أول حرف لكل خطوة).

### Step-by-Step Process (The DHCP Process)

1. **DHCP Discover:** 
الجهاز بيبعت رسالة للشبكة يقول: "أنا جديد هنا، حد يقدر يديني IP Address؟".
2. **DHCP Offer:** 
الـ DHCP Server بيرد عليه: "أيوه، خد الـ IP ده (مثلاً 192.168.1.10) ممكن تستخدمه".

3. **DHCP Request:**
الجهاز بيرد لتأكيد العرض: "تمام، ده ممتاز، أنا هبدأ استخدم الـ IP ده 192.168.1.10".
4. **DHCP ACK (Acknowledgement):**
5. الـ DHCP Server بيختم الكلام: "تمام، الـ IP ده بتاعك لمدة معينة (Lease duration زي 24 ساعة)".

### Definitions

- **DHCP:** Dynamic Host Configuration Protocol, used to automatically assign IP addresses to devices on a network.

> [!note] الـ DHCP مش بس بيدي IP، ده كمان بيحدد المدة اللي هيفضل الـ IP ده معاك فيها (Lease time).

### Exam-Style Questions
>[!Question]
>Explain the difference between a Switch and a Hub regarding packet handling.

>[!Answer]
> A Switch keeps track of connected devices and sends packets only to the intended target port, reducing traffic. 
> 
> A Hub (implied context) repeats packets to every port.

>[!Question]
>What are the four steps of the DHCP process?

>[!Answer]
>1. **Discover:** Device requests an IP.
>
>2. **Offer:** Server offers an IP.
>
>3. **Request:** Device accepts the IP.
>
>4. **ACK:** Server confirms and assigns the IP.

>[!Question]
>Why is Subnetting important for a business network?

>[!Answer]
>It provides Efficiency, Security (by separating departments), and Full Control over the network layout.

---
# Global Extraction

## Extracted Rules & Laws

- **Star Topology Rule:** If the central device fails, the entire network stops.
- **Ring Topology Rule:** A single break in the loop brings down the network unless it is bidirectional.
- **Bus Topology Rule:** If the backbone fails, the whole network fails.
- **Switch Rule:** Switches send packets only to the intended target, not to all ports.
- **ARP Rule:** Works strictly inside a local network (LAN) to map IP to MAC.

## Study Notes

- **Topologies:** Star is best for expansion but relies on the center. Ring is consistent but fragile. Bus is cheap but hard to maintain with scale.

- **Devices:** Switch is for creating a LAN (connecting devices). Router is for connecting WANs/LANs (connecting networks).

- **Subnetting:** Think of it as organizing a building into rooms for security and better flow.

- **ARP:** The bridge between Layer 3 (IP) and Layer 2 (MAC).

- **DHCP:** The automatic receptionist giving out room numbers (IPs) to new guests.


# Master Summary

- **Topologies:**
    - **Star:** Central device, isolated faults, total failure if center dies.
    - **Ring:** Closed loop, token passing (implied), break kills loop.
    - **Bus:** Single backbone, cheap, single point of failure.

- **Switch:** Aggregates devices, uses MAC, sends to specific port.

- **Router:** Connects networks, uses IP, performs routing paths.

- **Subnetting:** Splitting networks for Security, Efficiency, Control.

- **ARP:** Maps IP Address $\rightarrow$ MAC Address via Broadcast.

- **DHCP:** Automates IP assignment. Steps: Discover $\rightarrow$ Offer $\rightarrow$ Request $\rightarrow$ ACK.


# Glossary

- **Topology:** Physical layout of network connections.

- **Switch:** Device that connects multiple devices within the same network intelligently.

- **Router:** Device that routes data between different networks.

- **Subnetting:** Dividing a network into smaller sub-networks.

- **ARP:** Address Resolution Protocol (IP to MAC mapping).

- **DHCP:** Dynamic Host Configuration Protocol (Auto IP assignment).

- **Backbone:** Main cable in Bus topology.

- **ICMP:** Protocol used by Ping (mentioned in context of network testing, relevant background).

---
