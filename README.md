# -Multi-VRF-MPLS-Lab-with-MP-BGP-Multiple-IGPs

🌐 Multi-VRF MPLS & MP‑BGP Lab

## 🧩 1. Topology Diagram  

![Image](https://github.com/user-attachments/assets/63b337bc-e1e4-42ab-8e2f-41d3cb14920c)


---
## ⚙️ 2. Lab Overview
This hands-on EVE‑NG lab emulates a service-provider environment with two core PE routers (ISP‑A and ISP‑B), each hosting three VRFs:

RIP-VRF — connected to RIP customer routers (R3 & R6)

OSPF-VRF — connected to OSPF customer routers (R4 & R7)

EIGRP-VRF — connected to EIGRP customer routers (R5 & R8)

Each customer site advertises a single /32 prefix per VRF. Here's how everything fits together:

R3 — RIP → ISP-A(RIP-VRF) ── MP-BGP/MPLS ── ISP-B(RIP-VRF) → RIP — R6

R4 — OSPF → ISP-A(OSPF-VRF) ── MP-BGP/MPLS ── ISP-B(OSPF-VRF) → OSPF — R7

R5 — EIGRP → ISP-A(EIGRP-VRF) ── MP-BGP/MPLS ── ISP-B(EIGRP-VRF) → EIGRP — R8

## ✅ 3. Lab Results & Verification

### 🔍 3.1 VRF Route Tables  
![Image](https://github.com/user-attachments/assets/09556cda-a4f4-4719-825b-916b11f591af)

### 🔍 3.1.1 VRF Configuration On ISP Interfaces 

![Image](https://github.com/user-attachments/assets/63396799-4a50-4e06-8cc8-3b1f3b3b4cf5)

### 🔍 3.1.2 Routes Recived On Each Customer Router 

![Image](https://github.com/user-attachments/assets/a846e9e2-4d63-4a34-8597-d34a03907ffd)

  ### 🧪 3.2 End-to-End Ping Tests  
![Image](https://github.com/user-attachments/assets/a1960df7-0c57-4448-9641-aa46474ebc40)

  ### 🧪 3.2.1 Ping Teat To Each Customer From ISP 
  ![Image](https://github.com/user-attachments/assets/8257ef95-e294-417b-a1be-aacf45c5c16d)

- ## 🛠 4. Lab Setup Instructions

1. Import **`eve-ng-lab.unl`** into EVE‑NG.
2. Copy router config files from `configs/` into each lab router.
3. Start the lab and verify:
   - MPLS LDP adjacency:
     ```bash
     show mpls ldp neighbors
     ```
   - VRF routing tables:
     ```bash
     show ip route vrf RIP
     show ip route vrf OSPF
     show ip route vrf EIGRP
     ```
   - MP‑BGP vpnv4 neighbors & routes:
     ```bash
     show ip bgp vpnv4 vrf RIP
     show ip bgp vpnv4 vrf OSPF
     show ip bgp vpnv4 vrf EIGRP
     ```
   - MPLS label tables:
     ```bash
     show mpls label table
     show mpls forwarding-table
     ```
   

- ## 🔗 7. Lab Assets & GitHub

The EVE‑NG `.unl` file and all router configs are available in this repo. Start the lab locally, review the config, and experiment freely!

If you encounter issues or have suggestions, feel welcome to open an issue or connect with me. Happy networking! 🚀

---

*#EVE‑NG #MPLS #MPBGP #VRF #NetworkingLab* 
