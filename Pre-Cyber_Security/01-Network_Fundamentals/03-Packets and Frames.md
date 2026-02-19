---
title: "Network Fundamentals: TCP/IP, Protocols, and Data Transmission"
tags:
  - study
  - exam
  - networking
  - TCP-IP
  - encapsulation
date: 2026-01-26T14:08:00
status: studying
format: obsidian-md
---
---
# Network Data Units & Models

## Packets and Frames

### Detailed Explanation
في الـ Networking، الداتا بتتقسم لأجزاء صغيرة عشان تتنقل، بس المسمى بيختلف حسب الـ Layer اللي إحنا فيها جوه الـ OSI Model. عندنا مصطلحين مهمين جدًا ولازم تفرق بينهم: الـ **Packets** والـ **Frames**. الاتنين بيشيلوا داتا، بس كل واحد فيهم بيشتغل في مستوى مختلف.

الـ **Packet** دي وحدة البيانات في **Layer 3 (Network Layer)**. دي بتحتوي على المعلومات الخاصة بالـ Logical Addressing زي الـ IP Address (المصدر والوجهة) وشوية بيانات تانية في الـ Header بتاعها.

أما الـ **Frame**، دي وحدة البيانات في **Layer 2 (Data Link Layer)**. الـ Frame بتعمل **Encapsulation** للـ Packet (يعني بتحطها جواها) وبتزود عليها معلومات زيادة زي الـ MAC Address عشان التوصيل الفعلي بين الأجهزة.

> [!note]
> الـ Packet والـ Frame هما أجزاء من نفس الرسالة، بس الفرق في "الغلاف" والمعلومات اللي بتنضاف في كل مرحلة.

### Key Points Summary
- **Packet:** 
- بتشتغل في Layer 3، وفيها الـ IP Address.
- **Frame:** 
- بتشتغل في Layer 2، وبتغلف الـ Packet، وفيها الـ MAC Address.
- **Encapsulation:** 
- الـ Frame بتحتوي الـ Packet جواها.

### Headers Definition
كل Packet أو Frame بيبقى ليها **Header** (مقدمة) فيه معلومات تحكم مهمة:

* **Time to Live (TTL):**
* ده حقل بيحدد عمر الـ Packet جوه الشبكة عشان ما تفضلش تلف للأبد لو تاهت (Clogging up the network).
* **Checksum:**
* ده بيستخدم للتأكد من الـ Integrity بتاعة الداتا. لو الداتا اتغيرت أو باظت في السكة، الـ Checksum هيتغير والجهاز المستقبل هيعرف إنها Corrupt.
* **Source Address:**
* عنوان الـ IP للجهاز اللي بيبعت الداتا (عشان الرد يرجع له).
* **Destination Address:** 
* عنوان الـ IP للجهاز اللي رايحاله الداتا.

---
## TCP/IP Model

### Detailed Explanation
الـ **TCP/IP** هو الأساس اللي قايم عليه الإنترنت والشبكات الخاصة النهاردة. هو عبارة عن مجموعة بروتوكولات (Suite) بتنظم الاتصال. فكرته قريبة جدًا من الـ OSI Model، وبيستخدم نفس مبدأ الـ **Encapsulation** (تغليف الداتا) والـ **Decapsulation** (فك الغلاف) طول ما الداتا بتتحرك بين الـ Layers.

النموذج ده بيتكون من 4 Layers أساسية، عكس الـ OSI اللي كان 7.

### TCP/IP Layers Structure

1.  **Application Layer:** دي الطبقة اللي بتتعامل مع البرامج اللي المستخدم بيشوفها.
    * **Protocols:** HTTP, FTP, DNS, SMTP.
2.  **Transport Layer:** 
مسؤولة عن توصيل الداتا سواء بشكل Reliable (زي TCP) أو سريع (زي UDP).
    * **Protocols:** TCP, UDP.
3.  **Internet Layer:**
مسؤولة عن توجيه (Routing) الـ Packets باستخدام الـ IP Addresses.
    * **Protocols:** IP, ICMP, ARP.
4.  **Network Access Layer:** 
دي اللي بتبعت الداتا الخام (Raw Data) عبر الوصلات الفيزيائية.
    * **Protocols:** Ethernet, Wi-Fi, PPP.

### Comparison: TCP/IP vs. OSI Model

| OSI Model Layers | TCP/IP Model Layers | Common Protocols |
| :--- | :--- | :--- |
| **7. Application** | **Application Layer** | HTTP, FTP, SMTP, SSH, Telnet |
| **6. Presentation** | **Application Layer** | (Included in App Layer) |
| **5. Session** | **Application Layer** | (Included in App Layer) |
| **4. Transport** | **Transport Layer** | TCP, UDP |
| **3. Network** | **Internet Layer** | IP, ICMP, IPSec |
| **2. Data Link** | **Link Layer (Network Access)** | Ethernet, Wi-Fi |
| **1. Physical** | **Link Layer (Network Access)** | (Included in Link Layer) |

---
# Transmission Protocols

## TCP (Transmission Control Protocol)

### Detailed Explanation
الـ **TCP** هو بروتوكول **Connection-oriented**، يعني "بيهتم بالاتصال". قبل ما يبعت أي داتا، لازم يفتح اتصال مع الطرف التاني ويتأكد إنه جاهز. هو بروتوكول **Reliable** (موثوق)، بيضمن إن الداتا توصل كاملة وبنفس الترتيب الصحيح. لو حاجة وقعت في السكة، بيبعتها تاني.

عشان المميزات دي، الـ TCP بيبقى أبطأ شوية بسبب عمليات الفحص (Error checking) والـ Acknowledgment اللي بتتم.

### TCP Packet Contents (Headers)
الـ Packet بتاعة الـ TCP مليانة حقول مهمة (Headers) عشان تضمن الدقة دي:

1.  **Source Port:**
رقم البورت اللي بيبعت الداتا (بيكون Random من 0-65535).
2.  **Destination Port:** 
رقم البورت للخدمة اللي بنكلمها (زي بورت 80 للويب)، وده مش بيكون Random.
3.  **Source IP & Destination IP:** عناوين الأجهزة.
4.  **Sequence Number:** رقم عشوائي بيتحط لأول قطعة داتا عشان نرتبهم بعدين.
5.  **Acknowledgement Number (ACK):**
الرقم اللي بيقول "أنا استلمت الداتا دي ومستني اللي بعدها" (بيكون Sequence + 1).
6.  **Checksum:** 
معادلة رياضية للتأكد إن الداتا سليمة (Integrity).
7.  **Data:** الداتا الفعلية اللي بتتبعت.
8.  **Flags:** 
علامات بتحدد حالة الاتصال (زي SYN, FIN, ACK).

### Three-Way Handshake
دي الطريقة اللي الـ TCP بيفتح بيها الاتصال. لازم الـ Client والـ Server يسلموا على بعض الأول في 3 خطوات عشان يعملوا **Synchronisation**.

#### Step-by-Step Process
1.  **SYN (Synchronize):**
    * الـ Client بيبعت Packet فيها Flag اسمه **SYN** ورقم Sequence عشوائي (مثلاً 100).
    * المعنى: "أنا عايز أفتح معاك اتصال".
2.  **SYN-ACK:**
    * الـ Server بيرد بـ Packet فيها **SYN** و **ACK**.
    * الـ ACK بيكون 101 (يعني استلمت 100 ومستني 101).
    * الـ SYN بيكون برقم Sequence جديد من السيرفر (مثلاً 500).
    * المعنى: "وصلت رسالتك، وأنا كمان بفتح معاك اتصال".
3.  **ACK (Acknowledge):**
    * الـ Client بيرد بـ **ACK** رقمه 501.
    * المعنى: "تمام، يلا نبدأ نبعت داتا".

> [!tip]
> عشان تفتكرها: SYN (ممكن نكلم؟) -> SYN/ACK (أيوة ممكن، وأنا جاهز) -> ACK (تمام، بدأنا).

### TCP Flags Definitions
* **SYN:** 
بداية الاتصال (Synchronise).
* **ACK:** 
تأكيد الاستلام (Acknowledgement).
* **FIN:** 
إنهاء الاتصال بشكل سليم (Clean close).
* **RST:** 
إنهاء الاتصال فورًا وبشكل مفاجيء (Abruptly) لو حصل مشكلة أو خطأ.
* **PSH:** (Push Data) - ابعت الداتا حالاً (مشروحة ضمنياً في سياق الداتا).

### Closing a Connection
عشان نقفل الاتصال بأمان، بنعمل خطوات عكسية باستخدام الـ **FIN Flag**:
1.  الطرف الأول يبعت **FIN**.
2.  الطرف التاني يرد بـ **ACK**.
3.  الطرف التاني يبعت **FIN** كمان.
4.  الطرف الأول يرد بـ **ACK**.

---
## UDP (User Datagram Protocol)

### Detailed Explanation
الـ **UDP** هو "ابن العم المتهور" للـ TCP. هو بروتوكول **Connectionless** (مفيش اتصال مسبق) و **Stateless**. بيبعت الداتا فورًا من غير ما يتأكد إن الطرف التاني موجود أصلاً، ومن غير **Three-way handshake**.

هو **Unreliable** (غير موثوق) لأنه مش بيضمن وصول الداتا ولا ترتيبها، ومفيش Error correction. بس في المقابل هو **سريع جدًا** (Faster) و **Lightweight** (خفيف).

### Comparison: TCP vs. UDP

| Feature | TCP | UDP |
| :--- | :--- | :--- |
| **Connection** | Connection-oriented (Handshake موجود) | Connectionless (مفيش Handshake) |
| **Reliability** | Reliable (بيضمن الوصول والترتيب) | Unreliable (مفيش ضمانات) |
| **Speed** | أبطأ (بسبب الـ Overhead) | أسرع (Less Overhead) |
| **Use Cases** | Web Browsing, Email, File Transfer | Gaming, Streaming, DNS, DHCP |

### UDP Packet Contents
الـ Header بتاع الـ UDP بسيط وأصغر بكتير:
1.  **TTL:** 
عشان الـ Packet ما تلفش للأبد.
2.  **Source & Destination Address:** العناوين.
3.  **Source & Destination Port:** المنافذ.
4.  **Data:** البيانات.
* (لاحظ مفيش Sequence Number ولا Acknowledgement).

---
# Data Transmission Mechanics

## Encapsulation vs. Decapsulation

### Detailed Explanation
العمليتين دول هما رحلة الداتا جوه الـ Layers بتاعة الشبكة (سواء OSI أو TCP/IP).

### 1. Encapsulation (التغليف)
دي بتحصل لما الداتا بتنزل من فوق لتحت (من App لـ Physical) عشان تجهز للإرسال.
* **الفكرة:** كل Layer بتزود **Header** (أو Trailer) خاص بيها على الداتا.
* **الخطوات:**
* **Application:** الداتا الأصلية.
* **Transport:** 
 بنزود Source/Dest Ports + Seq Numbers (بقت Segment).
* **Network:** 
بنزود Source/Dest IP Addresses (بقت Packet).
* **Data Link:**
بنزود MAC Addresses + FCS للـ Error checking (بقت Frame).
* **Physical:** 
بتتحول لـ Bits (أصفار ووحايد) عشان تمشي في السلك.

### 2. Decapsulation (فك التغليف)
دي بتحصل لما الداتا توصل للجهاز المستقبل، وتطلع من تحت لفوق.
* **الفكرة:** كل Layer بتشيك على الـ Header بتاعها وتشيله وتبعت الباقي للي فوقها.
* **الخطوات:**
* **Physical:** 
 يستلم الـ Bits ويحولها.
* **Data Link:** 
يتأكد من الـ MAC ويشيل الـ Header.
* **Network:**
 يتأكد من الـ IP ويشيل الـ Header.
* **Transport:** 
يتأكد من الـ Ports ويشيل الـ Header.
* **Application:** يسلم الداتا الخام للبرنامج (زي المتصفح).

---
## Network Ports

### Detailed Explanation
الـ **Port** هو عبارة عن "باب افتراضي" (Virtual Door) على الجهاز أو السيرفر. الباب ده هو اللي بيسمحلك تتواصل مع خدمة محددة (Service) جوه الجهاز. الأرقام دي بتتراوح من 0 لـ 65535.

### Common Ports List
لازم تكون حافظ البورتات دي صم:

* **FTP (File Transfer Protocol):** Port **21** (لنقل الملفات).
* **SSH (Secure Shell):** Port **22** (للدخول الآمن والتحكم عن بعد - Text based).
* **HTTP (HyperText Transfer Protocol):** Port **80** (تصفح الويب غير المشفر).
* **HTTPS (HTTP Secure):** Port **443** (تصفح الويب المشفر والآمن).
* **SMB (Server Message Block):** Port **445** (لمشاركة الملفات والطابعات).
* **RDP (Remote Desktop Protocol):** Port **3389** (للدخول والتحكم بواجهة رسومية GUI).

> [!warning]
> خد بالك إن SSH (Port 22) بيستخدم للـ Administration الآمن بديل لـ Telnet لأنه مشفر، بينما RDP (Port 3389) بيستخدم لو عايز تشوف Desktop كامل.

---
# Global Extraction

# Extracted Rules & Laws
* **Connection Rule:**
الـ TCP لازم يبدأ بـ Three-way Handshake قبل نقل أي داتا.
* **Fragmentation Rule:** 
 الـ IP Packet بتتقسم لـ Frames في Layer 2 عشان تمشي في الشبكة المحلية.
* **Addressing Rule:** 
الـ Switch بيستخدم MAC Address (Layer 2)، والـ Router بيستخدم IP Address (Layer 3).

# Extracted Formulas
* **Sequence Logic:** Next Sequence Number = Current Sequence + Data Bytes (Conceptually).
* **ACK Logic:** ACK Number = Last Received Sequence + 1.

# Study Notes
* الـ **Encapsulation** بيحصل عند المرسل (Sender)، والـ **Decapsulation** بيحصل عند المستقبل (Receiver).
* الـ **Source Port** بيكون عشوائي، لكن الـ **Destination Port** بيكون ثابت ومعروف (Well-known) حسب الخدمة.
* الـ **TTL** وظيفته يمنع الـ Packets إنها تعمل Loop للأبد في الشبكة.
* الـ **Checksum** موجود في TCP و UDP و IP للتأكد إن الداتا ما وصلتش بايظة.

# Master Summary
* **Packet** في Layer 3، **Frame** في Layer 2.
* **TCP/IP Model** 4 طبقات: Application, Transport, Internet, Network Access.
* **TCP:** Reliable, Connection-oriented, Slow, 3-way handshake.
* **UDP:** Unreliable, Connectionless, Fast, No handshake.
* **Three-way handshake:** SYN -> SYN/ACK -> ACK.
* **Encapsulation:** 
إضافة Headers وأنت نازل في الـ Layers.
* **Ports:** 
أبواب للخدمات (21 FTP, 22 SSH, 80 HTTP, 443 HTTPS).

# Exam Notes
* سؤال متكرر: الفرق بين TCP و UDP (السرعة vs الموثوقية).
* سؤال متكرر: ترتيب خطوات الـ Handshake (مين بيبعت الأول؟ Client بيبعت SYN).
* الـ Flags مهمة جدًا: RST بتنهي الاتصال فجأة، FIN بتنهيه باحترام.
* احفظ أرقام البورتات (21, 22, 80, 443, 445, 3389) لأنها بتيجي في أسئلة الاختياري.
* الـ SSH (22) هو البديل الآمن للـ Telnet.

# Glossary
* **Packet:** 
وحدة بيانات في Network Layer.
* **Frame:** 
وحدة بيانات في Data Link Layer مغلفة للـ Packet.
* **TTL (Time To Live):**
عداد لانتهاء صلاحية الـ Packet.
* **Three-way Handshake:** 
عملية تأسيس الاتصال في TCP.
* **Encapsulation:**
تغليف البيانات بالـ Headers.
* **Port:** معرف رقمي للخدمة على الشبكة.
* **SYN:** Flag لبدء التزامن في الاتصال.
* **ACK:** Flag لتأكيد الاستلام.

---
