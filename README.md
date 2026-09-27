# AI-Probelm-Design-Task-1

1. Narrow AI Use Case
Retrieval-Augmented Generation (RAG) Q&A system restricted to answering employee questions strictly based on a provided set of internal HR documents.

2. The User
Standard company employees who need immediate, accurate answers regarding leave balances, expense reimbursement limits, and remote work policies without waiting 24-48 hours for an HR support ticket resolution.

3. Data Source
A small, static dataset of 12 approved internal PDF documents. This includes the 2024 Employee Handbook, the Travel & Expense Policy, and the IT Hardware Request Guidelines.

4. Constraints

Strict Grounding (Zero Hallucination Tolerance): The model must explicitly refuse to answer questions if the information is not contained within the 12 provided PDFs. It cannot rely on its pre-trained knowledge for company-specific policies.

Latency: The system must retrieve context and generate an answer in under 4 seconds to ensure it is faster than manually searching the document.

Data Privacy/Access: The source dataset must be scrubbed of any Personally Identifiable Information (PII) before being embedded into the vector database.

5. Evaluation Approach
The system will be evaluated against a "golden dataset" of 50 historically common HR questions paired with verified correct answers.

Automated Metrics: We will use RAGAS (Retrieval Augmented Generation Assessment) to programmatically measure two specific metrics:

Context Precision: Did the retrieval system pull the correct paragraphs from the PDFs?

Faithfulness: Can the generated answer be traced directly back to the retrieved context without injected hallucinations?

Human-in-the-Loop Review: An HR specialist will manually review the 50 outputs for tone appropriateness and strict policy alignment before the system is greenlit for employee use.
