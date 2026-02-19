---
title: Subnetting, IPv4 Classes, and NAT Fundamentals
tags:
  - study
  - exam
  - networking
  - subnetting
  - nat
date: 2026-01-26T16:33:00
status: studying
format: obsidian-md
---
---
# Subnet Mask Overview

## Subnet Mask Definition and Function

### Detailed Explanation
الـ **Subnet Mask** هو عبارة عن رقم مكون من **32-bit**، وظيفته الأساسية في الـ IP networks إنه يقسم الـ **IP address** لجزئين رئيسيين:
1.  **Network portion**:
وده الجزء اللي بيحدد الـ Network المحددة.
2.  **Host portion**: 
وده الجزء اللي بيحدد الأجهزة (الـ Hosts) جوه الـ Network دي.

لما بنشوف **Subnet mask** زي `255.255.255.0` (اللي ممكن يتكتب بصيغة `/24`)، ده معناه إن أول **24 bits** من الـ **IP address** دول ثابتين للـ Network، بينما الـ **8 bits** الأخيرة هما اللي متاحين للـ Hosts.

التقسيمة دي بتسمح بوجود Range من الـ IP addresses. على سبيل المثال، ممكن يكون عندنا Range بيبدأ من `192.168.66.1` لحد `192.168.66.254`. في الحالة دي:
* الـ address `192.168.66.0` بيعتبر هو الـ **Network address**.
* الـ address `192.168.66.255` بيعتبر هو الـ **Broadcast address**.

### Key Points Summary
* الـ **Subnet Mask** طوله **32-bit**.
* وظيفته تقسيم الـ **IP** لـ **Network portion** و **Host portion**.
* الـ `/24` بتشير لـ `255.255.255.0` (أول 24 bit للشبكة).

### Definitions
* **Subnet Mask**: A 32-bit number used in IP networks to divide an IP address into network and host portions.
* **Network Portion**: The part of the IP address that identifies the specific network.
* **Host Portion**: The part of the IP address that identifies the devices (hosts) within that network.

> [!tip] Subnet Mask Calculation
> 
> احسب عدد بتات الهوست  
> 32 − Prefix
> 
> احسب عدد العناوين  
> 2 ^ عدد بتات الهوست
> 
> اطرح العناوين المحجوزة  
> Network address  
> Broadcast address
> 
> عدد الأجهزة  
> (2 ^ عدد بتات الهوست) − 2
> 
> مثال  
> /24  
> 32 − 24 = 8  
> 2 ^ 8 = 256  
> 256 − 2 = 254
### Examples
**Example Setup:**
* **Subnet Mask**: `255.255.255.0` (/24).
* **Range Interpretation**:
    * First 24 bits are fixed.
    * Last 8 bits are available for hosts.
* **Resulting Addresses**:
    * **Network Address**: `192.168.66.0`.
    * **Usable Host Range**: `192.168.66.1` to `192.168.66.254`.
    * **Broadcast Address**: `192.168.66.255`.

---
# IPv4 Classes and Subnet Masks

## Class Classifications

### Detailed Explanation
الـ **IPv4** بيتقسم لـ Classes مختلفة، كل Class بيبقى ليه **Subnet Mask** افتراضي بيحدد عدد الـ Networks وعدد الـ Hosts المتاحين في كل Network.

**Class A:**
بتستخدم **Subnet Mask** `255.0.0.0`. هنا بنحجز **8 bits** بس للـ Network، وبنسيب **24 bits** كاملين للـ Host. ده بيدينا عدد ضخم جدًا من الـ Hosts في كل شبكة.

**Class B:**
بتستخدم **Subnet Mask** `255.255.0.0`. التقسيمة هنا بالتساوي، **16 bits** للـ Network و **16 bits** للـ Host.

**Class C:**
بتستخدم **Subnet Mask** `255.255.255.0`. هنا بنحجز **24 bits** للـ Network، وبيتبقى بس **8 bits** للـ Host، عشان كده عدد الـ Hosts قليل.

> [!tip] Networks Calculation
> 
> حدد فئة العنوان  
> Class A
> 
> اعرف عدد بتات الـ Network  
> Class A  
> 8 بتات للشبكة
> 
> اعرف البتات المحجوزة  
> أول بت ثابت  
> قيمته 0
> 
> احسب البتات المتغيرة  
> 8 − 1 = 7
> 
> احسب عدد الشبكات  
> 2 ^ عدد البتات المتغيرة
> 
> 2 ^ 7 = 128 Network
> 
> الخلاصة  
> Class A  
> عدد الـ Networks = 128
> 
> قاعدة عامة  
> عدد الـ Networks = 2 ^ (عدد بتات الـ Network − البتات المحجوزة)
> 
> اسأل نفسك  
> كم بت مستخدم للشبكة  
> وكم بت محجوز حسب الـ Class

### Rules / Laws / Principles

#### Class A Configuration
* **Subnet Mask**: `255.0.0.0`
* **Structure**: 8 bits (Network) -> 24 bits (Host).
* **Capacity**: 128 Networks.
* **Hosts per Network**: 16,777,216 hosts.

#### Class B Configuration
* **Subnet Mask**: `255.255.0.0`
* **Structure**: 16 bits (Network) -> 16 bits (Host).
* **Capacity**: 16,384 Networks.
* **Hosts per Network**: 65,536 hosts.

#### Class C Configuration
* **Subnet Mask**: `255.255.255.0`
* **Structure**: 24 bits (Network) -> 8 bits (Host).
* **Capacity**: 2,097,152 Networks.
* **Hosts per Network**: 256 hosts.

> [!tip] Reserved Bits Determination
> 
> اعرف نظام IPv4 الكلاسيكي  
> العنوان يتقسم Classes  
> كل Class له بتات ثابتة في البداية
> 
> البتات الثابتة تحدد الفئة  
> ولا تُستخدم في العد
> 
> Class A  
> أول بت = 0  
> عدد البتات المحجوزة = 1
> 
> Class B  
> أول بتين = 10  
> عدد البتات المحجوزة = 2
> 
> Class C  
> أول 3 بتات = 110  
> عدد البتات المحجوزة = 3
> 
> سبب الحجز  
> تمييز الفئات  
> منع التداخل  
> تسهيل التوجيه القديم
> 
> مثال تطبيقي  
> Class B  
> 16 بت للشبكة  
> 2 بت محجوز  
> البتات المتغيرة = 14  
> عدد الشبكات = 2 ^ 14
> 
> قاعدة ثابتة  
> عدد البتات المحجوزة = عدد البتات الثابتة لتعريف الـ Class
> 
> اسأل نفسك  
> ما هي الفئة  
> وكم بت ثابت في بدايتها

---
# Network Configuration Commands

## Checking IP and Subnet Mask

### Detailed Explanation
عشان نقدر نشوف إعدادات الـ Network الحالية زي الـ **IP address** والـ **Subnet mask** على الجهاز، بنستخدم أوامر مختلفة حسب نظام التشغيل (OS) اللي شغالين عليه.

لو شغالين على **Windows**، الأمر الأساسي هو `ipconfig`.
أما لو شغالين على **Linux/UNIX**، عندنا أكتر من خيار زي `ifconfig` أو الأمر الحديث `ip address show`، واللي ممكن نكتبه باختصار `ip a s`.

### Step-by-Step Process
**For Windows:**
1. Open Command Prompt.
2. Type `ipconfig`.

**For Linux/UNIX:**
1. Open Terminal.
2. Type `ifconfig` OR `ip address show` OR `ip a s`.

### Key Points Summary
* **Windows Command**: `ipconfig`.
* **Linux Commands**: `ifconfig`, `ip address show`, `ip a s`.

---
# NAT (Network Address Translation)

## Concept and Functionality

### Detailed Explanation
الـ **IPv4** نظريًا يقدر يدعم حوالي 4 مليار جهاز. لكن مع الانفجار الكبير في عدد الأجهزة (زي الـ PCs، الـ Smartphones، وأجهزة الـ IoT زي الكاميرات والتلفزيونات وحتى الغسالات)، مساحة الـ **IPv4** مابقتش كفاية.

عشان نحل المشكلة دي، تم تقديم تقنية اسمها **NAT** أو **Network Address Translation**. الفكرة الأساسية للـ **NAT** إنها بتسمح لعدد كبير من الـ **Private IP addresses** جوه شبكة معينة إنهم يوصلوا للـ Internet باستخدام **Public IP address** واحد بس.

### Examples
لو عندنا شركة فيها **20 computers**:
* **Without NAT**: 
هنحتاج **20 Public IP addresses** (واحد لكل جهاز).
* **With NAT**: 
هنستخدم **1 Public IP address** بس عشان نوفر Internet access لكل الـ 20 جهاز دول.

### Definitions
* **NAT (Network Address Translation)**: A technology introduced to solve the IPv4 shortage by mapping multiple private IP addresses to a single public IP address.

### Understanding Checkpoints
* **Why NAT?** Because IPv4 space is limited and devices are increasing rapidly.
* **How it works?** Translates multiple Private IPs to one Public IP.

---
# Global Extraction

## Extracted Rules & Laws
* **Subnet Mask /24 Rule**: First 24 bits are Network, last 8 bits are Host.
* **NAT Efficiency Rule**: Allows multiple private devices to share a single Public IP for internet access.
## Study Notes
* **Subnetting Basics**:
    * Divide IP into Network & Host.
    * Example: `255.255.255.0` (/24).
    * Network Address ends in `.0` (usually).
    * Broadcast Address ends in `.255` (usually).
* **IPv4 Classes**:
    * **Class A**: Massive hosts (16M+), Small nets. Mask: `255.0.0.0`.
    * **Class B**: Balanced (65k hosts). Mask: `255.255.0.0`.
    * **Class C**: Small hosts (256), Massive nets. Mask: `255.255.255.0`.
* **Commands**:
    * Windows: `ipconfig`.
    * Linux: `ifconfig`, `ip a s`.

## Master Summary
* **Subnet Mask** is a 32-bit number splitting IP into Network and Host portions.
* **Class A** supports ~16 million hosts (`/8`).
* **Class B** supports ~65,000 hosts (`/16`).
* **Class C** supports 256 hosts (`/24`).
* **NAT** solves IPv4 depletion by allowing private networks to access the internet via a single Public IP.

## Exam Notes
* **Identification**:
لازم تعرف تفرق بين الـ Classes من خلال الـ Subnet Mask بتاعهم (255.0.0.0 vs 255.255.0.0 vs 255.255.255.0).
* **Commands**: 
ركز في الفرق بين أوامر Windows (`ipconfig`) و Linux (`ifconfig` / `ip a s`).
* **NAT Purpose**:
السؤال ممكن ييجي عن فايدة الـ NAT الأساسية (توفير Public IPs).

## Glossary
* **Subnet Mask**: 32-bit number defining network and host bits.
* **Network Portion**: Identifies the network.
* **Host Portion**: Identifies devices within the network.
* **NAT**: Network Address Translation, maps private IPs to public IPs.
* **Broadcast Address**: Address used to communicate with all devices in the subnet (e.g., .255).

---
