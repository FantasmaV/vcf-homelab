# VCF 9.0 Homelab

A hands-on VMware Cloud Foundation 9.0.2 homelab built on 4x Intel NUC MS-01 mini PCs. This repo documents the bringup configuration, network topology, and deployment notes for a fully functional VCF management domain.

> ⚠️ All credentials and IPs in sample files have been sanitized. Never commit real passwords or license keys.

---

## Hardware

| Role | Device | Count |
|------|--------|-------|
| ESXi Hosts | Intel NUC MS-01 | 4 |
| Core Switch | Zyxel SG2210XMP | 1 |
| Access Switch | TP-Link Omada SX3008F | 1 |
| Edge/Firewall | OPNsense | 1 |

---

## Network Topology

```
ISP → Cable Modem → OPNsense → Zyxel SG2210XMP → Omada SX3008F → ESXi Hosts (esx01–esx04)
```

| Network | VLAN | Subnet |
|---------|------|--------|
| Management | 10 | 192.168.10.0/24 |
| vMotion | 20 | 192.168.20.0/24 |
| vSAN | 30 | 192.168.30.0/24 |

---

## VCF Stack

| Component | Version |
|-----------|---------|
| VCF | 9.0.2 |
| ESXi | 9.0 |
| vCenter | 9.0.2.0 |
| NSX | 9.0 |
| SDDC Manager | 9.0 |
| vSAN | OSA (ESA disabled) |

---

## Repo Structure

```
vcf-homelab/
├── README.md
└── bringup/
    └── vcf_bringup_sample.json   # Sanitized Cloud Builder bringup JSON
```

---

## Status

- [x] Network topology configured
- [x] VCF Cloud Builder bringup completed
- [x] SDDC Manager deployed
- [x] vCenter and 4-node vSAN cluster healthy
- [ ] NSX configuration and VPC topology (in progress)
- [ ] Workload domain deployment (coming soon)

---

## Notes & Lessons Learned

*Full deployment notes coming after bringup completion.*

---

## Author

**Randolph Barden**  
Senior VCF Consultant | VCF Architect 9.0 | VCAP VCF Operations & Automation  
[LinkedIn](https://www.linkedin.com/in/) | Montgomery, TX
