# Solo Agent Prompt Engineering Template (Comprehensive)

## Purpose
This template is designed for crafting effective, robust, and reusable prompts for **single-agent** LLM-based systems (e.g., ChatGPT, Claude, Gemini). It provides a structured method to guide an individual agent to complete a clearly defined task with precision, creativity, and consistency.

Solo-agent prompts are ideal when:
- The task has a linear or finite scope.
- Context and decision-making are localized.
- Agent specialization is sufficient.

---

## Template Architecture

### 1. **Agent Role Definition**
Clearly establish the agent's persona or function.
- Format: `You are [a highly skilled/expert/etc.] [role]`
- Purpose: Influences language style, domain expertise, and tone.

**Examples:**
- You are a senior data scientist with 10 years of experience in healthcare analytics.
- You are a certified cloud security consultant specializing in AWS infrastructure audits.

---

### 2. **Objective (Goal Definition)**
Articulate the exact outcome you expect.
- Format: `Your task is to [do X in context Y]`
- Avoid ambiguity or abstract goals.

**Examples:**
- Your task is to write a technical blog post explaining how Kubernetes horizontal pod autoscaling works.
- Your task is to analyze the following CSV data and summarize key business trends.

---

### 3. **Context and Background**
Provide relevant details, assumptions, and scenario.
- Include file descriptions, environment, user intent, business logic, or input data.
- Avoid overloading the agent with unnecessary noise.

**Examples:**
- The user is a junior developer who needs a beginner-friendly explanation.
- The CSV includes financial data from Q1–Q4 2024 across 5 regions.

---

### 4. **Constraints and Rules**
Define strict boundaries.
- Word count, tone, banned tools, required methods, time periods, perspectives.

**Examples:**
- Limit output to 500 words.
- Do not use Python libraries outside the standard library.
- Avoid speculative statements and ensure all facts are cited.

---

### 5. **Output Format and Style**
Define what the final output should look like.
- Markdown / JSON / Table / Bullet Points / Code Blocks / HTML
- Tone: professional, educational, empathetic, marketing, etc.

**Examples:**
- Format the output as a 3-section Markdown document: Summary, Key Findings, Action Items.
- Provide a JSON object with the following keys: `summary`, `risks`, `recommendations`.

---

### 6. **Verification and Reasoning**
(Optional but recommended)
- Ask the agent to perform sanity checks, verification passes, or explain its reasoning.
- Boosts reliability and transparency.

**Examples:**
- Before finalizing, double-check that each recommendation aligns with provided constraints.
- Include a short section explaining why each step was taken.

---

## Example: Solo Agent Prompt (Technical Task)

**Prompt:**
```
You are a senior DevOps engineer with expertise in AWS and Kubernetes.

Your task is to create a Terraform configuration that provisions an EKS cluster with:
- A managed node group
- Public and private subnets
- IAM roles for service accounts (IRSA)

Context:
The user is building a secure development environment for a SaaS application.
The region is `us-west-2`. Assume the VPC already exists.

Constraints:
- Use only Terraform v1.5+ syntax
- Do not include Helm charts or ArgoCD modules
- Ensure IRSA roles follow least privilege

Output Format:
Provide the code in Terraform blocks with clear comments. Add a final `README` section describing usage.

Style:
Professional and instructional
```

---

## Prompt Debugging & Optimization Tips
- If output is too verbose, reduce scope or clarify word count.
- If hallucination occurs, add context verification.
- Use `Chain-of-Thought` or `Step-by-step reasoning` if task requires judgment.

---

## Advanced Extensions
- **Prompt chaining**: Output of one solo-agent task feeds into another.
- **Multi-format output**: Combine markdown summary + JSON backend.
- **Function calling mode**: Use with LLMs that accept tool call arguments.

---

## Versioning & Reuse Guidelines
- Store prompts in Git repositories or Notion.
- Use variables in brackets (`[objective]`, `[context]`, etc.) to create parametric templates.
- Label each prompt with version, intended model (e.g., GPT-4-turbo), and test notes.

---

## License
MIT License – use and modify freely. Crediting the original author is appreciated.
