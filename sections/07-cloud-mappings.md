[← Back to index](../README.md) · **Section VII of VII**

# VII. Cloud-Specific Mappings

*Deliberately the last section, and deliberately separated from everything above it.*

**Why this is its own section:** the decision logic in Sections II–V is durable — it doesn't change when a vendor renames a service or ships a new model. The tables below *will* go stale. Keeping them isolated here means the core primer stays correct even as this page needs updates — and it's the easiest place in the whole repo for a PR to fix.

> 📌 **If you're reading this primer after mid-2026, assume the specific service names below have shifted. The pattern they map to (Sections III–IV) almost certainly hasn't.**

---

## 7.1 Capability tiers → providers

Maps Section 1.3's tiers to each provider's current lineup. Check each vendor's docs for the latest model names before quoting this in a proposal.

| Tier | Azure | AWS (Bedrock) | Anthropic (direct) |
|---|---|---|---|
| Fast / cheap | Smaller Azure OpenAI tier model | Smaller Bedrock-hosted model (e.g. Amazon Nova Micro/Lite, or a small partner model) | Claude Haiku family |
| Mid / balanced | Mid-tier Azure OpenAI model | Mid-tier partner model on Bedrock | Claude Sonnet family |
| Frontier / reasoning | Top-tier Azure OpenAI reasoning model | Top-tier partner model on Bedrock | Claude Opus family |

## 7.2 Core patterns → services

| Pattern (Section III) | Azure | AWS |
|---|---|---|
| **RAG — vector store** | Azure AI Search | OpenSearch Serverless / Bedrock Knowledge Bases |
| **RAG — orchestration** | Microsoft Agent Framework, Semantic Kernel, or Azure AI Foundry Agent Service | LangChain, Strands Agents, or Bedrock Agents |
| **Tool-using agent** | Azure AI Foundry Agent Service | Bedrock Agents / Bedrock AgentCore |
| **Multi-agent supervisor** | Multi-agent orchestration via Agent Framework / Semantic Kernel | Bedrock AgentCore with Strands "Agents as Tools" / supervisor pattern |
| **MCP / tool integration** | MCP support via Foundry Agent Service and SDK orchestrators | Bedrock AgentCore MCP server support |

## 7.3 Platform capabilities → services

| Capability (Section IV) | Azure | AWS |
|---|---|---|
| **GenAI gateway** | Azure API Management fronting Azure OpenAI / Foundry | Amazon API Gateway fronting Bedrock |
| **Guardrails** | Azure AI Content Safety | Amazon Bedrock Guardrails |
| **Observability / tracing** | Azure Monitor + Application Insights | Amazon CloudWatch + X-Ray |
| **Vector store (self-hosted option)** | Postgres + pgvector on Azure Database for PostgreSQL | Postgres + pgvector on Amazon RDS/Aurora |

## 7.4 Hosting decision, by compliance driver

The durable logic behind Section 1.3 and 4.3's hosting choices — this table changes far less often than the service-name tables above, because it's driven by compliance categories rather than product names.

| Driver | Typical answer |
|---|---|
| Must stay in-VPC / no data leaves your environment | Self-hosted open-weight model, or a cloud provider's VPC-isolated managed offering with a signed data-processing agreement |
| Regulated (HIPAA, financial services) but cloud-acceptable | Managed cloud offering with the appropriate compliance certification and a signed BAA / equivalent agreement in place |
| Already heavily committed to one cloud | Default to that cloud's native AI platform — switching cost usually outweighs marginal model-quality differences |
| No strong constraint, optimizing for capability | Evaluate top frontier models directly against your own eval suite (Section V) — don't assume the "biggest name" is the best fit without testing |

---

## How to keep this section current

This is the easiest section in the repo to contribute to without needing deep architecture judgment — if a service is renamed, deprecated, or a new tier-equivalent ships, that's a one-line PR. See [Contributing](../README.md#contributing).

---

**Previous:** [← VI. Industry Walkthroughs](06-industry-walkthroughs.md) · [Back to index](../README.md)
