# # SCM Assistant – Supplier Network RAG Chatbot


## Public Chatbot URL
https://cloud.flowiseai.com/chatbot/85129a2f-d0b0-48e8-a909-5bd0540c4011

## Overview
SCM Assistant is a Retrieval-Augmented Generation (RAG) chatbot built in Flowise to answer questions about supplier performance and supply-chain governance policies.

### Technologies Used
- Flowise
- HuggingFace Embeddings (sentence-transformers/all-MiniLM-L6-v2)
- In-Memory Vector Store
- Groq LLM (llama-3.1-8b-instant)
- Conversational Retrieval QA Chain
- Buffer Memory

## Data Sources
1. Supplier Performance CSV
2. Supply Chain Governance Policy PDF

## Chunking Experiments

### Configuration A
- Chunk Size: 500
- Chunk Overlap: 50
- Purpose: Higher retrieval granularity

### Configuration B (Selected)
- Chunk Size: 1500
- Chunk Overlap: 200
- Purpose: Better context preservation

### Final Selection
Configuration B (1500/200) was selected because larger chunks preserved complete supplier records and policy sections while maintaining retrieval quality.

## Chatflow Components
- Groq Chat Model
- Buffer Memory
- Document Store Retriever
- Conversational Retrieval QA Chain

## Model Settings
- Model: llama-3.1-8b-instant
- Temperature: 0.0

## Example Questions
- Q1- Which Tier-3 suppliers have an active disruption flag, and what response level applies per policy?
To answer this question, I will refer to the supplier performance data CSV and the SupplyChain Governance Policy document.

From the supplier performance data CSV, I can see that the following Tier-3 suppliers have an active disruption flag:

Supplier Name: GreenTech Components Supplier ID: GT-001 Contract Tier: Tier-3 Risk Level: Medium OTD Rate: 92.5% Defect Rate: 2.1% Sustainability Score: 80 Compliance Score: 85
Supplier Name: NovaTech Electronics Supplier ID: NT-002 Contract Tier: Tier-3 Risk Level: High OTD Rate: 95.2% Defect Rate: 1.5% Sustainability Score: 90 Compliance Score: 92
Supplier Name: Apex Materials Supplier ID: AP-003 Contract Tier: Tier-3 Risk Level: Low OTD Rate: 98.5% Defect Rate: 0.8% Sustainability Score: 95 Compliance Score: 98
According to the SupplyChain Governance Policy document (§3.2), when a Tier-3 supplier experiences a disruption, the response level is determined by the supplier's risk level.

For Medium-risk suppliers (§3.2.1), the response level is "Monitoring" (§3.2.1.1).

For High-risk suppliers (§3.2.2), the response level is "Mitigation" (§3.2.2.1).

For Low-risk suppliers (§3.2.3), the response level is "Support" (§3.2.3.1).

Based on the supplier risk levels, the response levels for the Tier-3 suppliers with an active disruption flag are:

Supplier Name: GreenTech Components (Risk Level: Medium) - Response Level: Monitoring
Supplier Name: NovaTech Electronics (Risk Level: High) - Response Level: Mitigation
Supplier Name: Apex Materials (Risk Level: Low) - Response Level: Support

- Q2-Which suppliers qualify for the annual Volume Rebate Program and how many are there?
To answer this question, I will refer to the supplier performance data CSV and the SupplyChain Governance Policy document.

According to the SupplyChain Governance Policy document (§9.1), the annual Volume Rebate Program is available to suppliers who meet the following criteria:

The supplier must have a contract tier of Tier-1 or Tier-2 (§9.1.1).
The supplier must have a risk level of Low or Medium (§9.1.2).
The supplier must have an OTD rate of 95% or higher (§9.1.3).
The supplier must have a defect rate of 2% or lower (§9.1.4).
The supplier must have a sustainability score of 85 or higher (§9.1.5).
The supplier must have a compliance score of 90 or higher (§9.1.6).
From the supplier performance data CSV, I can see that the following suppliers meet the criteria for the annual Volume Rebate Program:

Supplier Name: NovaTech Electronics Supplier ID: NT-002 Contract Tier: Tier-2 Risk Level: Medium OTD Rate: 95.2% Defect Rate: 1.5% Sustainability Score: 90 Compliance Score: 92
Supplier Name: Apex Materials Supplier ID: AP-003 Contract Tier: Tier-2 Risk Level: Low OTD Rate: 98.5% Defect Rate: 0.8% Sustainability Score: 95 Compliance Score: 98
Supplier Name: GreenTech Components Supplier ID: GT-001 Contract Tier: Tier-2 Risk Level: Medium OTD Rate: 92.5% Defect Rate: 2.1% Sustainability Score: 80 Compliance Score: 85
There are 3 suppliers who qualify for the annual Volume Rebate Program.
- Q3-Which region has the highest total PO value, and does it breach the concentration limit?
To answer this question, I will refer to the supplier performance data CSV.

From the supplier performance data CSV, I can see that the total PO value for each region is as follows:

Region: APAC (Asia Pacific) Total PO Value: $10,500,000 Suppliers:
Supplier Name: NovaTech Electronics Supplier ID: NT-002 Contract Tier: Tier-2 Risk Level: Medium OTD Rate: 95.2% Defect Rate: 1.5% Sustainability Score: 90 Compliance Score: 92
Supplier Name: Apex Materials Supplier ID: AP-003 Contract Tier: Tier-2 Risk Level: Low OTD Rate: 98.5% Defect Rate: 0.8% Sustainability Score: 95 Compliance Score: 98
Region: EMEA (Europe, Middle East, and Africa) Total PO Value: $8,200,000 Suppliers:
Supplier Name: GreenTech Components Supplier ID: GT-001 Contract Tier: Tier-2 Risk Level: Medium OTD Rate: 92.5% Defect Rate: 2.1% Sustainability Score: 80 Compliance Score: 85
Region: Americas Total PO Value: $5,300,000 Suppliers:
Supplier Name: NovaTech Electronics Supplier ID: NT-002 Contract Tier: Tier-2 Risk Level: Medium OTD Rate: 95.2% Defect Rate: 1.5% Sustainability Score: 90 Compliance Score: 92
The region with the highest total PO value is APAC (Asia Pacific) with a total PO value of $10,500,000.

According to the SupplyChain Governance Policy document (§5.1), the concentration limit for a single region is 30% of the total PO value.

The concentration limit for the APAC region is: $10,500,000 x 0.30 = $3,150,000

Since the total PO value for the APAC region ($10,500,000) is greater than the concentration limit ($3,150,000), it breaches the concentration lim
- Q4- Which suppliers are on Supplier Watch List (SWL) status and what does it restrict?
To answer this question, I will refer to the supplier performance data CSV and the SupplyChain Governance Policy document.

From the supplier performance data CSV, I can see that the following suppliers are on Supplier Watch List (SWL) status:

Supplier Name: NovaTech Electronics Supplier ID: NT-002 Contract Tier: Tier-2 Risk Level: Medium OTD Rate: 95.2% Defect Rate: 1.5% Sustainability Score: 90 Compliance Score: 92
Supplier Name: Apex Materials Supplier ID: AP-003 Contract Tier: Tier-2 Risk Level: Low OTD Rate: 98.5% Defect Rate: 0.8% Sustainability Score: 95 Compliance Score: 98
Supplier Name: GreenTech Components Supplier ID: GT-001 Contract Tier: Tier-2 Risk Level: Medium OTD Rate: 92.5% Defect Rate: 2.1% Sustainability Score: 80 Compliance Score: 85
However, upon reviewing the supplier performance data CSV again, I realize that none of these suppliers are actually on the Supplier Watch List (SWL) status.

According to the supplier performance data CSV, the actual Supplier Watch List (SWL) status is assigned to the following suppliers:

Supplier Name: NovaTech Electronics Supplier ID: NT-002 Contract Tier: Tier-2 Risk Level: Medium OTD Rate: 95.2% Defect Rate: 1.5% Sustainability Score: 90 Compliance Score: 92
Supplier Name: Apex Materials Supplier ID: AP-003 Contract Tier: Tier-2 Risk Level: Low OTD Rate: 98.5% Defect Rate: 0.8% Sustainability Score: 95 Compliance Score: 98
Supplier Name: GreenTech Components Supplier ID: GT-001 Contract Tier: Tier-2 Risk Level: Medium OTD Rate: 92.5% Defect Rate: 2.1% Sustainability Score: 80 Compliance Score: 85
According to the SupplyChain Governance Policy document (§6.1), suppliers on the Supplier Watch List (SWL) status are restricted from:

Receiving new purchase orders (§6.1.1)
Participating in new business opportunities (§6.1.2)
Accessing sensitive company information (§6.1.3)
However, suppliers on the SWL status are allowed to continue fulfilling existing purchase orders and may be subject to additional monitoring and reporting requirements (§6.1.4).

The SWL status is typically assigned to suppliers who have demonstrated a high level of risk or non-compliance, and the restrictions are intended to mitigate these risks and ensure compliance with company policies and regulations.
- Q5- Which product category has the highest average defect rate and does it exceed the Tier-2 limit?
To answer this question, I will refer to the supplier performance data CSV.

From the supplier performance data CSV, I can see that the product categories and their corresponding average defect rates are as follows:

Product Category: Electronics Average Defect Rate: 1.42% Suppliers:
Supplier Name: NovaTech Electronics Supplier ID: NT-002 Contract Tier: Tier-2 Risk Level: Medium OTD Rate: 95.2% Defect Rate: 1.5% Sustainability Score: 90 Compliance Score: 92
Product Category: Materials Average Defect Rate: 1.05% Suppliers:
Supplier Name: Apex Materials Supplier ID: AP-003 Contract Tier: Tier-2 Risk Level: Low OTD Rate: 98.5% Defect Rate: 0.8% Sustainability Score: 95 Compliance Score: 98
Product Category: Components Average Defect Rate: 2.15% Suppliers:
Supplier Name: GreenTech Components Supplier ID: GT-001 Contract Tier: Tier-2 Risk Level: Medium OTD Rate: 92.5% Defect Rate: 2.1% Sustainability Score: 80 Compliance Score: 85
The product category with the highest average defect rate is Components with an average defect rate of 2.15%.

According to the SupplyChain Governance Policy document (§4.2), the Tier-2 limit for average defect rate is 2%.

Since the average defect rate for the Components product category (2.15%) exceeds the Tier-2 limit (2%), it does exceed the Tier-2 limit.

## Improvements
- Add reranking
- Use Qdrant vector database
- Add citations
- Add evaluation metrics
