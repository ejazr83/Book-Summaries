## Lateral Movement

Lateral movement is the ultimate aim for threat actors to find data of value or compromise additional assets and resources. This is where systemic compromise can be achieved. 

**Resource lateral movement techniques**
Lateral movement attacks occur due to two vectors:
1. Privileged attacks: Password guessing , brute force, pass the hash etc
2. Asset Attacks: missing vulnerability, patch and config management ( Basic cyber hygiene )

**Resource Lateral movement techniques**
Resources | Privileged Attack Vector | Asset Attack Vector
---|---|---
Operating system | Credential, certificates, or hash-based attacks | Vulnerabilities, exploits, and misconfigurations
Applications | Credential, certificates, or application-to-application attacks | Vulnerabilities, exploits, misconfigurations, insecure architectures, and end of life
Containers | Credential, certificates, or insecure connectivity (lack of zero trust) | Vulnerabilities, exploits, misconfigurations, insecure architectures, and agile DevOps
Virtual machines | Credential or hash- or hypervisor-based credential attacks | Vulnerabilities, exploits, misconfigurations, insecure architectures and agile DevOps, and CPU- and memory-based vulnerabilities
Accounts | Credential theft or abuse or identity theft | Credential theft, abuse, memory-scraping, and insecure credential storage 
Identities | Credential reuse, credential theft | Inappropriate account linkage



**Key Point**: For Asset attacks concepts like Zero-trust or JIT and PAM will not work. Need basic cyber hygiene practices in place for asset protection

For Privileged attack vector: concepts of Zero-trust and JIT will help in mitigation
 - **Zero trust** is a security model based on the principle of maintaining strict access controls and not trusting anyone, anywhere, at any time, even those already inside the network perimeter, by default.
 - **Just-in-time and Just-Enough-Admin privileged access** is a strategy that aligns real-time requests for usage of privileged accounts directly with entitlements, workflow, and appropriate access policies.
 