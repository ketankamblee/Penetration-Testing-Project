# Penetration-Testing-Project
Penetration testing on Mediroza General Hospital Website.
# ⚠️ Liabitlity Disclaimer
I have performed these activities only on the Website where I had secured written permission or the devices/systems that I own myself. All these materials are for education and research purpose only. Do not use anything from here to break the law. The instructor, the authors and Networkwalks are not responsible for what you do with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record. In most countries unauthorised access is a crime even when nothing is damaged.

**Author:** Ketan Kamble  
**Batch:** B083 | Week 4  
**Target:** https://medirozahospital.com  
**Engagement Type:** Black-box Penetration Test  
**Duration:** 5 Days  
**Authorization:** Written permission granted by Mediroza General Hospital (via NetworkWalks training engagement)


# 📌 1. Executive Summary
This engagement identified three critical vulnerabilities in Mediroza General Hospital's web infrastructure: an authentication bypass via SQL injection on the patient portal, a publicly exposed database backup containing staff and shareholder records, and weak/dictionary-crackable passwords protecting confidential patient lab reports. Together, these findings would allow an unauthenticated attacker to access any patient's medical records and the hospital's internal HR and ownership data without any valid credentials.

# 2. Scope and Methodology
Scope: Full black-box penetration test limited to medirozahospital.com and its subpaths. No social engineering, denial-of-service, or out-of-scope testing was performed.  

Tools Used: `whois`, `nslookup`, `dnsrecon`, `whatweb`, `wafw00f`, `curl`, `networkwalks hash calculator`, `networkwalks password cracker`

**Approach:**
1. Passive reconnaissance — WHOIS, DNS records, HTTP headers, technology fingerprinting (`whatweb`, `wafw00f`)
2. Content discovery — reviewed `robots.txt` and `sitemap.xml` for disallowed/hidden paths
3. Directory and file enumeration on disallowed paths (`/old/`, `/patient/`, `/staff/`)
4. Authentication testing on discovered login forms
5. Post-exploitation file retrieval and offline password cracking
