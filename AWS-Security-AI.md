AWS AI — US Government Regulatory Standards (Pinoy Version) 🇵🇭
  
  Mga Standards na Kailangan Sundin para sa US Government Compliance
  
  ───────────────────────────────────────────────────────────────────────────────────────
  
  1. FedRAMP (Federal Risk and Authorization Management Program)
  
  Ano to: Standardized na security framework para sa lahat ng cloud services na ginagamit
  ng US government agencies.
  Pinoy analogy: Parang ISO certification ng gobyerno — bago ka maka-supply sa kanila,
  kailangan mong pumasa sa security audit nila. Walang FedRAMP authorization = walang
  government contract.
  
  Sa AWS AI context:
  
  - AWS GovCloud (US) regions ay FedRAMP High authorized
  - Kung ang AI solution mo ay para sa US federal agency, kailangan naka-deploy sa
  FedRAMP-authorized na region
  - SageMaker at Bedrock available sa GovCloud
  
  ───────────────────────────────────────────────────────────────────────────────────────
  
  2. NIST (National Institute of Standards and Technology)
  
  Ano to: Nag-p-publish ng cybersecurity frameworks at AI standards na sinusunod ng US
  government at private sector.
  Pinoy analogy: Parang DOST pero sa America — sila yung nag-se-set ng technical
  standards na sinusunod ng lahat.
  
  Key NIST frameworks para sa AI:
  
  ┌─────────────────────────────┬────────────────────────────────────────────────────┐
  │ Framework                   │ Para saan                                          │
  ├─────────────────────────────┼────────────────────────────────────────────────────┤
  │ NIST AI RMF (AI Risk        │ Pano i-manage ang risks ng AI — bias,              │
  │ Management Framework)       │ transparency, accountability                       │
  ├─────────────────────────────┼────────────────────────────────────────────────────┤
  │ NIST 800-53                 │ Security at privacy controls — required para sa    │
  │                             │ federal systems                                    │
  ├─────────────────────────────┼────────────────────────────────────────────────────┤
  │ NIST 800-171                │ Para sa contractors na may access sa Controlled    │
  │                             │ Unclassified Information (CUI)                     │
  ├─────────────────────────────┼────────────────────────────────────────────────────┤
  │ NIST Cybersecurity          │ Overall cybersecurity best practices               │
  │ Framework (CSF)             │                                                    │
  └─────────────────────────────┴────────────────────────────────────────────────────┘
  
  Sa AWS AI context:
  
  - AWS Bedrock Guardrails helps implement NIST AI RMF principles (transparency,
  fairness, accountability)
  - SageMaker Clarify addresses NIST AI bias detection requirements
  
  ───────────────────────────────────────────────────────────────────────────────────────
  
  3. HIPAA (Health Insurance Portability and Accountability Act)
  
  Ano to: Proteksyon ng health/medical data ng patients. Kung ang AI mo nag-p-process ng
  medical records, kailangan HIPAA-compliant.
  Pinoy analogy: Parang Data Privacy Act natin (RA 10173) pero specifically para sa
  medical records. Kung may nakita kang lab results ng pasyente sa AI system, kailangan
  protected yun.
  
  Sa AWS AI context:
  
  - AWS signs a BAA (Business Associate Agreement) — legal na agreement na protected ang
  health data
  - SageMaker at Bedrock ay HIPAA-eligible services
  - Kailangan i-encrypt ang PHI (Protected Health Information) at rest and in transit
  - Hindi pwedeng i-send ang patient data sa non-HIPAA-eligible na services
  
  ───────────────────────────────────────────────────────────────────────────────────────
  
  4. PCI-DSS (Payment Card Industry Data Security Standard)
  
  Ano to: Security standard para sa lahat ng nag-h-handle ng credit card data. Kung ang
  AI mo nag-p-process ng payment info, kailangan PCI-compliant.
  Pinoy analogy: Parang BSP regulations para sa banks — kung humahawak ka ng pera o card
  details ng tao, may strict na rules ka na kailangan sundin.
  
  Sa AWS AI context:
  
  - Kung ang AI/ML model mo nag-a-analyze ng transaction data for fraud detection,
  kailangan PCI-DSS compliant ang setup
  - AWS infrastructure ay PCI-DSS Level 1 certified (pinaka-mataas)
  - Pero ikaw pa rin ang responsible sa application layer — encryption, access controls,
  logging
  
  ───────────────────────────────────────────────────────────────────────────────────────
  
  5. SOC 2 (System and Organization Controls)
  
  Ano to: Audit report na nagpapatunay na secure ang handling ng customer data —
  security, availability, confidentiality.
  Pinoy analogy: Parang COA audit pero para sa private companies — may third-party na
  nag-c-check kung tama yung controls mo.
  
  Sa AWS AI context:
  
  - AWS services (including SageMaker, Bedrock) covered ng SOC 2 Type II reports
  - Importante para sa enterprise customers na nag-r-require ng audit evidence
  
  ───────────────────────────────────────────────────────────────────────────────────────
  
  6. Executive Order 14110 (Biden's AI Executive Order)
  
  Ano to: 2023 US Presidential order na nag-r-require ng safety testing, transparency, at
  accountability para sa AI systems — lalo na yung ginagamit ng government.
  Pinoy analogy: Parang Executive Order ng Presidente na nag-m-mandate ng specific rules
  para sa AI — lahat ng government agencies kailangan sumunod.
  
  Key requirements:
  
  - AI safety testing bago i-deploy sa government
  - Transparency — kailangan i-disclose kung AI-generated ang output
  - Bias testing at fairness assessments
  - Red-teaming ng AI models
  
  Sa AWS AI context:
  
  - Bedrock Guardrails — content filtering, topic blocking
  - SageMaker Clarify — bias detection at model explainability
  - CloudTrail — audit trail ng lahat ng AI API calls
  
  ───────────────────────────────────────────────────────────────────────────────────────
  
  7. ITAR (International Traffic in Arms Regulations)
  
  Ano to: Controls export ng defense-related data. Kung ang AI mo nag-p-process ng
  military/defense data, kailangan ITAR-compliant.
  Pinoy analogy: Parang export controls ng DND — hindi pwedeng lumabas ng bansa yung
  classified military info.
  
  Sa AWS AI context:
  
  - AWS GovCloud (US) supports ITAR workloads
  - Data stays within US borders, US persons only ang may access
  
  ───────────────────────────────────────────────────────────────────────────────────────
  
  🎯 Quick Reference Table
  
  ┌────────────────────┬─────────────────────────────┬───────────────────────────────┐
  │ Standard           │ Kung ang AI mo ay...        │ Kailangan mo ng...            │
  ├────────────────────┼─────────────────────────────┼───────────────────────────────┤
  │ FedRAMP            │ Para sa US federal agency   │ GovCloud deployment,          │
  │                    │                             │ authorized services           │
  ├────────────────────┼─────────────────────────────┼───────────────────────────────┤
  │ NIST 800-53/AI RMF │ Para sa government o        │ Security controls, AI risk    │
  │                    │ regulated industry          │ management                    │
  ├────────────────────┼─────────────────────────────┼───────────────────────────────┤
  │ HIPAA              │ Nag-p-process ng medical    │ BAA, encryption, access       │
  │                    │ data                        │ controls                      │
  ├────────────────────┼─────────────────────────────┼───────────────────────────────┤
  │ PCI-DSS            │ Nag-h-handle ng credit card │ Encryption, network           │
  │                    │ data                        │ segmentation, logging         │
  ├────────────────────┼─────────────────────────────┼───────────────────────────────┤
  │ SOC 2              │ May enterprise customers    │ Audit reports, security       │
  │                    │                             │ controls                      │
  ├────────────────────┼─────────────────────────────┼───────────────────────────────┤
  │ EO 14110           │ Deployed sa US government   │ Safety testing, transparency, │
  │                    │                             │ bias checks                   │
  ├────────────────────┼─────────────────────────────┼───────────────────────────────┤
  │ ITAR               │ Nag-p-process ng defense    │ GovCloud, US-only access      │
  │                    │ data                        │                               │
  └────────────────────┴─────────────────────────────┴───────────────────────────────┘
  
  ───────────────────────────────────────────────────────────────────────────────────────
  
  💡 Pano Ito Nag-a-apply sa AWS AI Services?
  
  ┌────────────────────┬──────────────────────────────────────────────────────────────┐
  │ AWS Service        │ Pano tumutulong sa compliance                                │
  ├────────────────────┼──────────────────────────────────────────────────────────────┤
  │ Bedrock Guardrails │ Content filtering, PII redaction, topic blocking (NIST AI    │
  │                    │ RMF, EO 14110)                                               │
  ├────────────────────┼──────────────────────────────────────────────────────────────┤
  │ SageMaker Clarify  │ Bias detection, model explainability (NIST AI RMF, EO 14110) │
  ├────────────────────┼──────────────────────────────────────────────────────────────┤
  │ AWS CloudTrail     │ Audit logging ng lahat ng API calls (FedRAMP, SOC 2,         │
  │                    │ PCI-DSS)                                                     │
  ├────────────────────┼──────────────────────────────────────────────────────────────┤
  │ AWS KMS            │ Encryption at rest at in transit (HIPAA, PCI-DSS, FedRAMP)   │
  ├────────────────────┼──────────────────────────────────────────────────────────────┤
  │ AWS GovCloud       │ Isolated region para sa government workloads (FedRAMP, ITAR) │
  ├────────────────────┼──────────────────────────────────────────────────────────────┤
  │ IAM + VPC          │ Access control at network isolation (lahat ng standards)     │
  ├────────────────────┼──────────────────────────────────────────────────────────────┤
  │ AWS Artifact       │ Download ng compliance reports (SOC 2, PCI-DSS, FedRAMP)     │
  └────────────────────┴──────────────────────────────────────────────────────────────┘
  
  ───────────────────────────────────────────────────────────────────────────────────────
  
  Bottom line: Hindi enough na "gumagana" ang AI solution mo. Para sa US government,
  kailangan compliant — may proper encryption, access controls, audit trails, bias
  testing, at authorized infrastructure. AWS provides the tools, pero shared
  responsibility — ikaw ang responsible sa pag-configure nang tama.
