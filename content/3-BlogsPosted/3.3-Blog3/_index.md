---
title: "Blog 3"
date: 2026-06-16
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The information below is for reference only. Please **do not copy it verbatim** into your report, including this warning.
{{% /notice %}}

# REFLECTING ON A MODERN ARCHITECTURE FOR KYC MODERNIZATION USING SERVERLESS & AGENTIC AI ON AWS

Recently, I came across an insightful article that analyzed an AWS and IBM whitepaper proposing a modern architecture for Know Your Customer (KYC) processes in the banking industry using Agentic AI, event-driven architecture, and AWS managed services. What makes the article particularly valuable is that it not only explains the proposed architecture but also critically evaluates the assumptions and limitations of the original whitepaper. This perspective highlights an important lesson: an architecture that looks elegant on paper is not necessarily ready for production deployment.

## Key Takeaways

* **Problem Context:** KYC is a mandatory regulatory process that includes identity verification, sanctions screening, risk assessment, and maintaining audit trails. Traditional KYC systems often rely on batch processing, causing new customer onboarding to take several days.

* **Well-Designed Architectural Decisions:**
  * Amazon MSK is used in an event-driven architecture to process each KYC request in real time instead of waiting for scheduled batch jobs.
  * A Supervisor Agent coordinates multiple specialized Sub-Agents (document verification, sanctions screening, fraud detection, etc.), routing requests based on confidence scores (auto-approval, additional verification, or escalation to human reviewers).
  * Retrieval-Augmented Generation (RAG) combined with a knowledge base ensures that AI agents always reference the latest regulatory requirements, reducing hallucinations caused by outdated training data.
  * AgentCore Gateway connects cloud-native AI services with on-premises core banking systems, making the architecture suitable for financial institutions that cannot fully migrate to the cloud.

* **Areas That Require Further Validation:**
  * Claims regarding processing speed improvements and confidence thresholds for automatic approval lack supporting experimental results or pilot studies.
  * Legal responsibility remains with the financial institution when AI makes incorrect decisions (such as rejecting legitimate applications or approving fraudulent ones). Therefore, explainability must be strengthened to comply with regulations such as the EU AI Act.
  * The security section does not address emerging threats such as deepfake identity documents, synthetic identity fraud, or prompt injection attacks targeting AI agents.
  * The Total Cost of Ownership (TCO) analysis does not include operational costs such as monitoring model drift, maintaining the knowledge base, or integrating with legacy systems.

## Personal Reflection

The article concludes that the technical architecture—including event-driven design, multi-agent systems, and Retrieval-Augmented Generation (RAG)—provides an excellent reference model that can be applied beyond KYC scenarios. However, performance claims and marketing-oriented statements should always be independently validated before deploying such an architecture in production environments handling sensitive financial data.

## References

Original AWS article:
<https://aws.amazon.com/.../modernizing-kyc-with-aws...>

Article discussed:
<https://www.facebook.com/share/p/1LS3B6w8Jy/>