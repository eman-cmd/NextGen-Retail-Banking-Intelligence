# Bank Policy Semantic Search Engine (Lightweight RAG Demo)

An intelligent, local Natural Language Processing (NLP) retrieval engine designed to parse internal banking documentation and match natural language user queries directly to correct institutional policies without risking data hallucinations or requiring external API costs.

---

## 🛠️ Technical Implementation & Architecture

In digital banking ecosystems like **Mashreq**, speed, data privacy, and extreme factual accuracy are critical. This engine bypasses resource-heavy external downloads by deploying a localized vector processing layout:

* **Text Vectorization**: Implemented `Scikit-Learn`'s `TfidfVectorizer` (with English stop-word filtration) to map unstructured policy text strings into multi-dimensional numerical vector matrices.
* **Semantic Retrieval Engine**: Programmed a local algorithmic lookup using `NumPy` and **Cosine Similarity Math** to measure the exact geometric angle between a user's conversational inquiry and the indexed policy vectors.
* **Zero-Hallucination Guardrails**: Functions strictly within a verified local knowledge base, guaranteeing that user responses are grounded explicitly in compliance documentation.

---

## 📊 Live System Verification

The engine was rigorously evaluated using conversational, ambiguous user inputs that did not contain exact keyword matches. The system successfully mapped inputs to the precise corporate policies with high mathematical confidence scores:

1. **User Question**: *"How do I cancel a fraudulent charge on my card?"*
   * **Retrieved Bank Policy**: Customers can dispute credit card transactions within 60 days of the statement date by filling out Form 404-B.
2. **User Question**: *"What yield do I get on the premium savings option?"*
   * **Retrieved Bank Policy**: The standard interest rate for a Premium Savings Account is 4.25% annually, with a minimum deposit of $5,000.
3. **User Question**: *"How much cash can I pull out from the machine today?"*
   * **Retrieved Bank Policy**: The daily ATM cash withdrawal limit across all standard debit cards is capped tightly at $1,000 per account.

---

## 🚀 Business Value for Modern Banking
* **Operational Workflow Optimization**: Accelerates internal customer service agent response times by instantly surfacing obscure policy clauses.
* **Enhanced Client Personalization**: Powers the logic required for conversational virtual assistants to answer complex financial inquiries securely.
* **Data Privacy Compliance**: Processes data entirely locally without transmitting proprietary bank data or customer interactions to third-party public cloud APIs.
