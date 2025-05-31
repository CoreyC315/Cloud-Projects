# 🛡️ Deploying a Secure Windows Server in Azure Using Bastion and RDP

This project demonstrates how to securely deploy and manage a Windows Server 2022 virtual machine in Microsoft Azure using a Bastion host for initial access and transitioning to Remote Desktop Protocol (RDP) via a public IP address with restricted access. It replicates a real-world enterprise scenario where secure and segmented access to virtual machines is critical.

---

## 🚀 What I Did

- Created an Azure Virtual Network (VNet) with properly segmented subnets for compute and Bastion services
- Deployed and configured a Bastion host to securely access a Windows Server VM without exposing public IPs
- Applied fine-tuned Network Security Group (NSG) rules to control inbound/outbound traffic
- Transitioned to direct RDP access by assigning a public IP to the VM and locking it down to a specific IP range
- Implemented cost-saving measures by deallocating and deleting unnecessary resources post-usage

---

## 🧠 Skills Demonstrated

- Azure Virtual Network (VNet) design
- Subnet planning and isolation
- Network Security Groups (NSGs) and rule configuration
- Bastion host deployment and usage
- Public IP assignment and secure RDP setup
- Azure resource cost management
- Windows Server 2022 deployment and initial configuration

---

## 🧭 Architecture Overview

Azure Virtual Network (VNet)  
├── Subnet: Bastion  
│   └── Bastion Host (used for secure access without public IP)  
└── Subnet: VM  
    └── Windows Server 2022 VM  
        ├── Initially accessed via Bastion  
        ├── Later accessed via RDP with a public IP (restricted via NSG)  
        └── NSG applied to control traffic  


## 📷 Screenshots

Screenshots of key steps are available in the `screenshots/` directory:
- Virtual Network and subnet setup
- NSG rule configuration
- Bastion deployment and portal access
- RDP session using public IP
- DNS and IP validation
- VM deallocation to prevent billing

---

## 📄 Step-by-Step Lab Notes

All detailed steps and explanations are available in [`documentation/lab-notes.md`](documentation/lab-notes.md), including:
- Portal navigation tips
- Rule explanations (e.g., `Calvin` CIDR range)
- Lab-specific justifications
- Resource teardown instructions

---

## 💡 Lessons Learned

- **Segmentation matters**: Using multiple subnets improves control over security and traffic flow
- **Least privilege**: NSG rules should be as tight as possible—even for temporary lab environments
- **Cost awareness**: Azure billing can add up quickly if VMs or Bastion hosts are left running
- **Transition flexibility**: Starting with Bastion for initial lockdown, then pivoting to RDP access when needed, models real-world security postures

---

## 🧰 Tools & Technologies

- Microsoft Azure Portal
- Azure Bastion
- Windows Server 2022
- RDP (Remote Desktop Protocol)
- Network Security Groups
- Public/Private IP management

---

## 📌 How to Reproduce

1. Clone this repo
2. Follow the step-by-step guide in `lab-notes.md`
3. Use the Azure Portal (or CLI/PowerShell) to replicate the setup
4. Optionally, export your own ARM templates to automate deployment

---

## 🔒 Security Notes

This lab uses minimal exposure principles by:
- Using Bastion (no public IP) for initial access
- Limiting RDP access to a specific CIDR range (`Calvin`)
- Deleting unused resources (like Bastion) post-deployment

---

## ✅ Status

✅ Complete  
🧪 Rebuilt for demonstration and portfolio use  
📌 Safe for public viewing (no sensitive credentials or access)

---

## 📎 License

This project is for educational purposes only and may be reused or adapted with attribution.

---

