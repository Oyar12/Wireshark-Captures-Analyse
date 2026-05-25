# DNS Investigation

This folder contains the technical analysis of DNS traffic based on the packet capture `dns.cap`.

---

## 1. General Information

- **Total packets:** 38
- **Capture duration:** 278.879 seconds
- **Protocol:** DNS over UDP/53
- **Analysis performed:** 2026-05-20  
- **Analyst:** Yasser OUEDRAOGO

---

## 2. Actors (IP Flows)

- **Client (Source):** 192.168.170.8
- **DNS Server (Destination):** 192.168.170.20
- **Transport:** UDP
- **Source Port:** 32795
- **Destination Port:** 53

(Based on first packet in the capture.)

---

## 3. DNS Query Analysis

- **Packet #:** 1
- **Transaction ID:** 0x1032
- **Queried domain:** google.com
- **Record type requested:** TXT

---

## 4. DNS Response Analysis

- **Packet #:** 2
- **Response Transaction ID:** 0x1032 (matches the query)
- **Result/data returned:** v=spf1 ptr ?all
- **TTL (cache duration):** 270 seconds

---

## 5. Conclusion

This investigation of a basic DNS exchange demonstrates how a client (192.168.170.8) queries a DNS server (192.168.170.20) for a TXT record related to google.com, receiving a Sender Policy Framework (SPF) response. The exchange is completed in just 530 microseconds with correct Transaction IDs matching in both query and reply, confirming an error-free conversation. This captures a standard use case in email authentication where SPF records are checked.

---

Lab performed and documented by Yasser OUEDRAOGO.
