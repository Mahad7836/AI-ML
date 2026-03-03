# AI Security Nuggets – Notes

**Course Completed:** AI Security Nuggets – The Video Series  
**Platform:** Cisco Networking Academy (NetAcad)

---

## 1. AI Security Overview & Legislation

### Core Concept
AI security extends beyond traditional cybersecurity. It includes governance, regulatory compliance, lifecycle risk management, and adversarial resilience.

### Key Points
- AI systems introduce new attack surfaces:
  - Models
  - Training data
  - Prompts
  - APIs
  - Retrieval pipelines
- Security must address:
  - **Confidentiality** – Prevent training data leakage
  - **Integrity** – Protect against model poisoning/tampering
  - **Availability** – Prevent model abuse and denial-of-service
- Regulatory requirements are evolving globally.
- Organizations must align AI systems with legal, ethical, and compliance standards.

### Takeaway
AI security is both a technical and governance challenge.

---

## 2. AI Security Program Implications

### Core Concept
AI must be integrated into existing enterprise security programs rather than treated as a standalone function.

### Program-Level Impacts
- Update risk management frameworks to include:
  - Model risk
  - Data risk
  - Autonomous decision risk
- Expand threat modeling to address:
  - Prompt injection
  - Model misuse
  - Data poisoning
- Implement AI-specific logging and monitoring.
- Conduct adversarial testing and AI red teaming.

### Takeaway
AI security requires collaboration across security, legal, compliance, data science, and engineering teams.

---

## 3. Risks in AI & Best Practices (OWASP + MITRE ATLAS Alignment)

### Major AI Risks
- Prompt injection attacks
- Training data poisoning
- Model inversion / sensitive data extraction
- Excessive agent autonomy
- Insecure output handling
- AI supply chain compromise

### Framework Alignment
- OWASP Top 10 for LLMs → Practical risk categorization
- MITRE ATLAS → Adversarial tactics & techniques for ML systems

### Best Practices
- Strict input and output validation
- Rate limiting and access controls
- Dataset integrity validation
- Continuous monitoring
- Adversarial testing before production deployment

### Takeaway
Structured frameworks make AI threats measurable and actionable.

---

## 4. AI Supply Chain Security

### Risk Areas
- Pre-trained third-party models
- Open-source ML libraries
- Embedding and vector database providers
- Cloud AI services

### Threats
- Backdoored or poisoned models
- Vulnerable dependencies
- Data contamination
- Shadow AI deployments

### Controls
- Model provenance verification
- Software Bill of Materials (SBOM) for AI components
- Vendor risk assessments
- Secure MLOps pipelines
- Dependency scanning

### Takeaway
AI supply chains are broader and often less visible than traditional software supply chains.

---

## 5. RAG & LLM Stack Security

### What is RAG?
Retrieval-Augmented Generation (RAG) combines an LLM with external knowledge sources, expanding functionality and attack surface.

### Key Risks
- Malicious document injection
- Data leakage from retrieval systems
- Prompt injection via retrieved content
- Unauthorized access to knowledge bases

### LLM Stack Components to Secure
- User interface
- Prompt layer
- Model layer
- Retrieval pipeline
- Vector database
- Data storage
- External APIs

### Security Controls
- Validate data before ingestion
- Enforce role-based access control (RBAC)
- Output filtering and sanitization
- Context boundary enforcement
- Monitor abnormal retrieval behavior

### Takeaway
Securing AI applications requires protecting the entire stack — not just the model.

---

# Overall Themes & Strategic Insights

- AI security must cover the full lifecycle.
- Governance and technical controls must align.
- AI threat modeling differs significantly from traditional application security.
- Framework-driven approaches improve risk clarity.
- RAG architectures significantly increase complexity and risk exposure.

---

## Personal Reflection

Completing this series reinforced that AI security is not a niche discipline — it is rapidly becoming foundational to modern cybersecurity strategy. As AI adoption accelerates, security programs must evolve just as quickly to address model risk, supply chain exposure, and adversarial techniques.

---

# Tags
AI Security | Cybersecurity | LLM Security | RAG Security | AI Governance | Secure AI | MLOps Security