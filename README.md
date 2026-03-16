# 🖨️ Network Printer Configuration — Cisco Packet Tracer

![Cisco Packet Tracer](https://img.shields.io/badge/Cisco-Packet%20Tracer-1BA0D7?style=for-the-badge&logo=cisco&logoColor=white)
![Networking](https://img.shields.io/badge/Topic-Network%20Configuration-green?style=for-the-badge)
![Level](https://img.shields.io/badge/Level-Beginner-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

---

## 📋 Project Description

This project demonstrates how to configure a **shared network printer** accessible by multiple PCs on the same local network using **Cisco Packet Tracer**. It is a beginner-friendly lab focused on core networking concepts including IP addressing, subnetting, and Layer-2 switching.

A single **Cisco 2960 Switch** connects **5 PCs** and **1 Network Printer** on the `192.168.1.0/24` subnet. Each PC can successfully ping and communicate with the printer — simulating a real-world office printer setup.

---

## 🗺️ Network Topology

```
        PC1               PC2               PC3
   192.168.1.10      192.168.1.20      192.168.1.30
        |                 |                 |
        +--------+--------+-----------------+
                 |
          [ Cisco 2960 Switch ]
                 |
        +--------+--------+
        |                 |
       PC4               PC5
  192.168.1.40      192.168.1.50
        |
  [ Network Printer ]
   192.168.1.100
```

---

## 🖥️ Devices Used

| Device           | Model            | Role              | Quantity |
|------------------|------------------|-------------------|----------|
| PC               | Generic PC       | End Host          | 5        |
| Switch           | Cisco 2960       | Layer-2 Switch    | 1        |
| Network Printer  | Generic Printer  | Shared Printer    | 1        |

---

## 🌐 IP Address Table

| Device          | IP Address      | Subnet Mask     | Default Gateway |
|-----------------|-----------------|-----------------|-----------------|
| PC1             | 192.168.1.10    | 255.255.255.0   | 192.168.1.1     |
| PC2             | 192.168.1.20    | 255.255.255.0   | 192.168.1.1     |
| PC3             | 192.168.1.30    | 255.255.255.0   | 192.168.1.1     |
| PC4             | 192.168.1.40    | 255.255.255.0   | 192.168.1.1     |
| PC5             | 192.168.1.50    | 255.255.255.0   | 192.168.1.1     |
| Network Printer | 192.168.1.100   | 255.255.255.0   | 192.168.1.1     |

> **Subnet:** `192.168.1.0 /24` — All devices on the same broadcast domain.

---

## ⚙️ Configuration Steps

### Step 1 — Add Devices
Open Cisco Packet Tracer and drag the following from the panel:
- 1× Cisco 2960 Switch
- 5× Generic PCs
- 1× Generic Printer

### Step 2 — Connect with Cables
Use **Copper Straight-Through** cables to connect each PC and the Printer to the switch.

### Step 3 — Configure Each PC
Click each PC → **Desktop** → **IP Configuration** → Set **Static IP**:

| PC  | IP Address    |
|-----|---------------|
| PC1 | 192.168.1.10  |
| PC2 | 192.168.1.20  |
| PC3 | 192.168.1.30  |
| PC4 | 192.168.1.40  |
| PC5 | 192.168.1.50  |

Subnet Mask: `255.255.255.0` | Default Gateway: `192.168.1.1`

### Step 4 — Configure the Printer
Click **Printer** → **Config** tab → **FastEthernet0**:
```
IP Address   : 192.168.1.100
Subnet Mask  : 255.255.255.0
Default GW   : 192.168.1.1
```

### Step 5 — Test Connectivity
On any PC, open **Desktop → Command Prompt** and run:
```bash
ping 192.168.1.100
```
✅ You should receive successful replies from the printer.

---

## ✅ Test Results

| Source | Source IP       | Target IP       | Result  |
|--------|-----------------|-----------------|---------|
| PC1    | 192.168.1.10    | 192.168.1.100   | ✅ Pass |
| PC2    | 192.168.1.20    | 192.168.1.100   | ✅ Pass |
| PC3    | 192.168.1.30    | 192.168.1.100   | ✅ Pass |
| PC4    | 192.168.1.40    | 192.168.1.100   | ✅ Pass |
| PC5    | 192.168.1.50    | 192.168.1.100   | ✅ Pass |

---

## 📚 Concepts Covered

- ✅ **Static IP Addressing** — Manual assignment of IPs to all devices
- ✅ **Subnetting** — Understanding `/24` subnet and host range
- ✅ **Layer-2 Switching** — MAC-based frame forwarding via Cisco 2960
- ✅ **Network Device Integration** — Printer configured as a network node
- ✅ **ICMP Ping Testing** — Verifying connectivity between hosts

---

## 📁 Project Structure

```
network-printer-config/
│
├── Network_Printer_Config.pkt       # Cisco Packet Tracer file
├── Network_Printer_Config_Report.docx  # Full lab report (Word)
└── README.md                        # This file
```

---

## 🚀 How to Open

1. Install [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) (free with Cisco NetAcad account)
2. Clone this repository:
   ```bash
   git clone https://github.com/your-username/network-printer-config.git
   ```
3. Open `Network_Printer_Config.pkt` in Cisco Packet Tracer
4. Follow the steps in this README or the attached Word report

---

## 🛠️ Requirements

- Cisco Packet Tracer 7.x or later
- No physical hardware required — fully simulated

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use it for learning and educational purposes.

---

## 🙋 Author

Made with ❤️ for networking learners.  
Feel free to ⭐ this repo if you found it helpful!
