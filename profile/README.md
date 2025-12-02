# Bombadil Systems

**Security Testing Tools for Professional Validation**

Bombadil Systems develops security testing frameworks for penetration testers, red teams, and security consultancies. Our tools address real-world challenges in validating security controls and testing defensive systems.

---

## Featured Projects

### 🔧 Veriduct
**Format Destruction for Security Testing**

Veriduct systematically tests whether security controls detect based on behavior rather than just signatures. It destroys file format signatures while maintaining perfect reconstruction capability.

**Validation Results:**
- **Production Malware:** 143 detection events → 0 across Cobalt Strike, Emotet, ValleyRAT
- **EICAR Baseline:** 65/68 → 0/68 on VirusTotal
- **Behavioral Analysis:** ANY.RUN sandbox identifies processed files as benign
- **Perfect Reconstruction:** SHA256 hash verification confirms bit-for-bit identical reassembly

**Key Capabilities:**
- Header randomization (destroys format signatures)
- Salted chunking (removes sequence information)
- Perfect reconstruction with cryptographic verification
- Systematic framework for DLP/EDR testing

**Use Cases:**
- Penetration testing (validate client DLP behavioral detection)
- Red team operations (test EDR trust models)
- Security validation (gap analysis: signature vs. behavioral detection)

**Repository:** [https://github.com/Bombadil-Systems/Veriduct-Core](https://github.com/Bombadil-Systems/Veriduct-Core)  
**Website:** [veriduct.com](https://veriduct.com)  
**Status:** Active development | Free version available | Commercial version Q1 2026

---

## About Bombadil Systems

Founded in 2025, Bombadil Systems focuses on building practical security tools that address real-world testing challenges. Our research emphasizes rigorous technical implementation and responsible disclosure practices.

**Core Philosophy:**
- Security through understanding, not obscurity
- Tools built for professional security testing with proper authorization
- Emphasis on validation and reproducible results
- Responsible research and disclosure

**Founder:** Christopher Aziz  
**Contact:** chris@bombadil.systems  
**Website:** [bombadil.systems](https://bombadil.systems)

---

## What's Next

### Current Status
- ✅ Veriduct free version available (GitHub)
- ✅ Technique validated (VirusTotal, ANY.RUN, live malware)
- ✅ Presenting at DEF CON DC862 (December 5, 2025)
- ✅ Commercial version in development

### Next Steps
- 📋 Vendor notification (responsible disclosure to EDR vendors)
- 💬 Community feedback (gathering input on direction)
- 🔬 Early access program (limited availability, Q1 2026)
- 🤝 Seeking testing partners with EDR lab access

**Interested in testing partnerships or early access?** Contact chris@bombadil.systems

---

## Commercial Licensing

Professional licensing available for Veriduct and future tools.

**Veriduct Commercial License:**
- **Status:** In development - Early access Q1 2026
- **Features:** Semantic Shatter Mapping, XOR Entanglement, Substrate Poisoning, variable chunking
- **Support:** Professional support and consulting available
- **Contact:** chris@bombadil.systems

**Free Version:**
- Available now on GitHub
- Basic format destruction (header randomization + salted chunking)
- Perfect for proof-of-concept and educational use
- MIT License with commercial use restrictions

---

## Presentations

**DEF CON DC862 - December 5, 2025**  
*"Veriduct: Format Destruction for Security Testing"*

---

## Legal & Responsible Use

**⚠️ All Bombadil Systems tools are designed for authorized security testing only.**

Users must:
- ✅ Obtain explicit written authorization before testing systems
- ✅ Use only on data they are authorized to access and process
- ✅ Comply with all applicable laws and regulations
- ✅ Follow responsible disclosure for identified vulnerabilities
- ✅ Maintain appropriate data handling and retention practices

**Unauthorized use may violate computer fraud, data protection, or other laws.**

---

## Connect

- **Website:** [bombadil.systems](https://bombadil.systems)
- **GitHub:** [@reapermunky](https://github.com/reapermunky) (founder)
- **Veriduct:** [veriduct.com](https://veriduct.com)

---

**Note:** This is the official GitHub presence for Bombadil Systems LLC. Individual repositories may have specific licensing terms and usage guidelines.

**Bombadil Systems: Testing frameworks for security professionals who verify instead of trust.**
