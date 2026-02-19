---
title: OSI Model & Transport Protocols (TCP vs UDP)
tags:
  - study
  - exam
  - networking
  - OSI_Model
  - TCP_UDP
date: 2026-01-22T14:30:00
status: studying
format: obsidian-md
---
---
# What is OSI Model?

## Detailed Explanation
الـ **OSI Model** (Open Systems Interconnection Model) هو موديل أساسي وضروري جدًا في الـ Networking. فكرته ببساطة إنه بيوفر Framework أو إطار عمل بيحدد القواعد اللي الأجهزة المتوصلة ببعض في الشبكة هتمشي عليها عشان تبعت وتستقبل وتفهم الـ Data.

أهم فايدة للـ **OSI Model** إنه بيخلي الأجهزة اللي وظائفها وتصميمها مختلف تقدر تتكلم مع بعضها عادي جدًا في نفس الشبكة. طالما الـ Data مبعوتة وبتمشي تبع القواعد الموحدة للـ **OSI Model**، يبقى الأجهزة التانية هتقدر تفهمها وتتعامل معاها.

## Key Points Summary
* الـ **OSI Model** هو Framework بينظم إرسال واستقبال الـ Data.
* بيسمح للأجهزة المختلفة (Different designs/functions) إنها تتواصل مع بعض.
* بيضمن إن الـ Data تكون مفهومة (Uniformity) لكل الأطراف.

## Definitions
- **OSI Model**: An essential model used in networking providing a framework dictating how devices send, receive, and interpret data.

---
# The 7 Layers of OSI Model

## Layers Breakdown (7 to 1)

### Detailed Explanation
الـ **OSI Model** بيقسم عملية الاتصال لـ 7 طبقات (Layers)، كل طبقة مسؤولة عن وظيفة محددة. الترتيب ده مهم جدًا وبيبدأ من فوق (عند الـ User) لحد تحت (عند الكابلات).

#### Layer 7 - Application Layer
دي الطبقة اللي بتكون أقرب حاجة للـ End user. وظيفتها إنها بتقدم الـ Network services للـ Applications اللي إنت بتستخدمها زي الـ Web browsers أو برامج الإيميلات.
* **Examples:** HTTP, HTTPS, FTP, SMTP, DNS.

#### Layer 6 - Presentation Layer
الطبقة دي بتجهز الـ Data عشان تكون "صالحة للاستخدام" (Usable format) للـ Application layer. هي اللي بتعمل ترجمة (Translates)، تشفير (Encrypts)، وضغط (Compresses) للبيانات.
* **Examples:** SSL/TLS encryption, JPEG, MP3.

#### Layer 5 - Session Layer
دي المسؤولة عن إدارة الـ Sessions (الجلسات) بين الأجهزة. يعني هي اللي بتعمل Start و Maintain و End للـ Connections.
* **Examples:** NetBIOS, RPC, PPTP.

#### Layer 4 - Transport Layer
هنا بيحصل التحكم في نقل الـ Data. الطبقة دي مسؤولة إن الـ Delivery يكون Reliable (مضمون) أو Unreliable (مش مضمون بس سريع). كمان بتعمل Segmentation (تقسيم الداتا)، و Flow control، و Error correction.
* **Examples:** TCP, UDP.

#### Layer 3 - Network Layer
الطبقة دي بتعمل Routing (توجيه) للـ Data بين الأجهزة عبر شبكات مختلفة (Different networks). بتستخدم الـ Logical addressing اللي هو الـ IP Addresses.
* **Data Name:** Packets.
* **Examples:** IP, ICMP, OSPF.

#### Layer 2 - Data Link Layer
دي بتنقل الـ Data بين جهازين موجودين في **نفس** الشبكة (Same network). بتستخدم الـ Physical addresses اللي هي الـ MAC addresses.
* **Data Name:** Frames.
* **Examples:** Ethernet, PPP, Switches.

#### Layer 1 - Physical Layer
دي بتمثل الـ Hardware الفعلي ونقل الـ Raw bits (الأصفار والوحايد).
* **Examples:** Cables, Hubs, Wi-Fi signals, Fiber optics.

### Key Points Summary
* **Layer 7 (Application):** User interface & Services (HTTP/FTP).
* **Layer 6 (Presentation):** Formatting & Encryption.
* **Layer 5 (Session):** Session Management (Start/Stop).
* **Layer 4 (Transport):** Delivery & Segmentation (TCP/UDP).
* **Layer 3 (Network):** Routing & IP Addresses (Packets).
* **Layer 2 (Data Link):** Local delivery & MAC Addresses (Frames).
* **Layer 1 (Physical):** Hardware & Bits.

> [!tip]
> عشان تحفظ ترتيب الـ Layers، ابدأ من 7 لـ 1 (من الـ Application للـ Physical) أو العكس، بس خليك عارف إن الـ Data بتنزل من 7 لـ 1 عند الـ Sender وتطلع من 1 لـ 7 عند الـ Receiver.
> 
> All people seem to need **double pizzas**.

---
# Data Flow in OSI Model

## How Data Moves

### Detailed Explanation
لما تيجى تبعت Data من جهاز لجهاز تاني، العملية بتمشي بخطوات منظمة جدًا:
1.  عند الـ **Sender**: الـ Data بتتحرك **لتحت** (Down) من الـ Application Layer (7) لحد الـ Physical Layer (1).
2.  عند الـ **Receiver**: الـ Data بتتحرك **لفوق** (Up) من الـ Physical Layer (1) لحد الـ Application Layer (7).

### Step-by-Step Process
1.  **Application (7):**
الـ Application بتاع اليوزر (زي المتصفح) بيعمل الـ Data اللي عايز يبعتها.
2.  **Presentation (6):** 
الـ Data بيحصلها Encryption أو Compression أو Translation للفورمات المناسب.
3.  **Session (5):**
بيتم فتح Communication session مع الجهاز المستقبِل.
4.  **Transport (4):** 
الـ Data بتتقسم لـ Segments، وبتاخد Port numbers، وبتتجهز للنقل (سواء TCP أو UDP).
5.  **Network (3):**
كل Segment بياخد IP address عشان يتعمل له Routing، وهنا بيتحول لـ **Packet**.
6.  **Data Link (2):**
الـ IP packet بيتحط في إطار (Frame) مع الـ MAC address عشان يوصل جوه الشبكة المحلية (Local network).
7.  **Physical (1):**
الـ Frames بتتحول لإشارات كهربائية (Electrical signals) أو نبضات ضوئية (Light pulses) أو موجات راديو وتتبعت عبر الـ Medium.

---
# Transport Protocols: TCP vs UDP

## 1. TCP (Transmission Control Protocol)

### Detailed Explanation
الـ **TCP** هو بروتوكول بيركز على الموثوقية (Reliability). هو **Connection-oriented**، يعني لازم يفتح اتصال الأول قبل ما يبعت أي Data. بيضمن إن كل الـ Data وصلت وبنفس الترتيب الصحيح (Correct order). عشان كده هو بيعتبر أبطأ شوية لإنه بيعمل Error checking و Acknowledgment لكل حاجة بتوصل.

* **Use Cases:** Web browsing (HTTP/HTTPS), Email (SMTP), File transfers (FTP).

### Key Characteristics
* **Reliable:** بيضمن وصول الداتا.
* **Ordered:** بيضمن الترتيب.
* **Error Correction:** بيصلح الأخطاء.
* **Heavy:**
   * بيحتاج Resources أكتر وأبطأ بسبب الـ Overhead.

## 2. UDP (User Datagram Protocol)

### Detailed Explanation
الـ **UDP** هو عكس الـ TCP، هو بروتوكول "سريع بس متهور". بيشتغل بنظام **Connectionless** ==> (شقلب واقلب)، يعني بيبعت الـ Data علطول من غير ما يتأكد إن فيه اتصال اتفتح أصلاً. هو **Unreliable**، يعني مفيش ضمان إن الداتا توصل، ولا إنها توصل بالترتيب. بس الميزة الكبيرة إنه **Faster** (أسرع) لإنه معندوش Overhead كتير.

* **Use Cases:** Streaming, Online Gaming, VoIP, DNS queries.

### Key Characteristics
* **Fast:** نقل سريع جداً.
* **Low Overhead:**
* استهلاك أقل للـ Resources.
* **Unreliable:** 
* مفيش ضمان وصول (No guarantee of delivery).
* **No Order:** مفيش تحكم في الترتيب.

> [!warning]
> نقطة امتحان مهمة: الفرق الجوهري إن **TCP** = Reliable but slower
> 
> لكن **UDP** = Fast but no guarantees.

---
# Comparison Table: TCP vs UDP

| Feature | TCP | UDP |
| :--- | :--- | :--- |
| **Type** | Connection-oriented (3-way handshake) | Connectionless (No handshake) |
| **Reliability** | Guaranteed delivery | No guarantee of delivery |
| **Order** | In-order delivery | Packets may arrive out of order |
| **Error Checking** | Error detection and correction | No built-in error correction |
| **Speed** | Slower | Faster |
| **Resource Usage** | High | Low |
| **Examples** | Web (HTTP), Email (SMTP) | Streaming, Gaming, VoIP, DNS |

---
# Study Notes & Exam Focus

## Packets vs Frames
> [!note]
> خد بالك من الفرق في المصطلحات حسب الـ Layer:
> * في **Layer 3 (Network)**: الـ Data اسمها **Packet** (فيها IP Header).
> * في **Layer 2 (Data Link)**: الـ Packet بتتحط جوه **Frame** (فيها MAC Address).

## Important Concepts Summary
* **Encapsulation:** 
* عملية إضافة الـ Headers والـ Trailers للداتا وهي نازلة من Layer 7 لـ Layer 1.
* **Decapsulation:** 
* عملية فك الـ Headers والداتا طالعة من Layer 1 لـ Layer 7.
* **Session Layer:** 
* هي المسؤولة عن فتح وقفل الـ Connections.
* **Presentation Layer:**
* هي المسؤولة عن الـ Encryption والـ Compression (زي الـ JPEG و MP3).

## Exam-Style Questions

>[!Question]
>**Which layer of the OSI model is responsible for routing data across different networks using IP addresses?**

>[!Answer]
>Layer 3 - Network Layer.

>[!Question]
>**If you are streaming a live video, which transport protocol is most likely being used and why?**

>[!Answer]
>UDP is used because speed is more important than reliability in live streaming; dropped frames are acceptable, but buffering/lag is not.

>[!Question]
>**Which layer ensures that data is in a usable format for the application, handling tasks like encryption?**

>[!Answer]
>Layer 6 - Presentation Layer.

>[!Question]
>**Explain the main difference between TCP and UDP regarding connection establishment.**

>[!Answer]
>TCP is connection-oriented and establishes a connection before sending data (using mechanisms like the 3-way handshake), while UDP is connectionless and sends data immediately without establishing a connection.

---
# Extracted Rules & Principles
* **OSI Rule:** Devices generally communicate by sending data down the stack (7->1) on the sender side and up the stack (1->7) on the receiver side.
* **Addressing Rule:** IP addresses are used at Layer 3 (Network), while MAC addresses are used at Layer 2 (Data Link).
* **Reliability Principle:** Use TCP when accuracy is critical (Files, Web, Email). Use UDP when speed is critical (Voice, Video, Gaming).

# Glossary
* **OSI Model:** Open Systems Interconnection Model.
* **LAN:** Local Area Network.
* **Packet:** A piece of data at Layer 3 (Network Layer).
* **Frame:** A piece of data at Layer 2 (Data Link Layer) encapsulating the packet.
* **TCP:** Transmission Control Protocol (Reliable).
* **UDP:** User Datagram Protocol (Unreliable/Fast).
* **IP Address:** Logical address used for routing (Layer 3).
* **MAC Address:** Physical address used for local delivery (Layer 2).

---
