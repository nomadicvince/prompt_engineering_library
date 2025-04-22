# Golden Prompt Engineering Framework (Full Edition)

## Overview
The Golden Prompt Framework is a **universal prompt architecture** for building intelligent, reusable, and context-aware instructions for AI agents. It applies to both **solo** and **multi-agent** systems and is designed for maximum flexibility, precision, and adaptability across domains.

This framework enables:
- **Rapid deployment** of prompts in production LLM applications
- **Modular prompt design** for automation workflows
- **Systematic reasoning and decision chains**
- **Prompt tuning and testing** using structured parameters

---

## Template Structure

### 1. **Role Declaration**
Set the AI’s identity and expertise.
> "You are a [role] with deep expertise in [domain]."

**Purpose:** Establishes domain authority and behavioral expectations.

**Example:**
> You are a senior AI policy analyst specializing in international law and algorithmic transparency.

---

### 2. **Mission Objective**
Define the exact task or transformation required.
> "Your task is to [deliver, analyze, generate, summarize, review] [target]."

**Example:**
> Your task is to write a two-page policy summary for a new international AI ethics treaty.

---

### 3. **Structured Reasoning Chain**
Define steps the AI should follow to think before answering.
> Step 1: Identify…
> Step 2: Compare…
> Step 3: Generate…
> Step 4: Validate…

**Purpose:** Reduces hallucinations, ensures depth, adds traceability.

**Example:**
```
Step 1: Extract top-level treaty provisions.
Step 2: Map provisions to existing national frameworks.
Step 3: Highlight overlapping and conflicting clauses.
Step 4: Propose potential amendments.
```

---

### 4. **Constraints and Operating Assumptions**
Clarify what the AI should or shouldn’t do.
> "Do not use speculative sources. Use only peer-reviewed documents. Limit output to 750 words."

Also specify:
- Tone
- Citations
- Date range
- Tools allowed (e.g., Python, regex, Markdown)

---

### 5. **Output Specification**
Describe the desired format and structure explicitly.
- JSON, Markdown, YAML
- Tables, charts, nested lists
- Summary + Appendix

**Example:**
> Return a Markdown report with three sections: Executive Summary, Observations, Recommendations. Include bullet-point callouts.

---

### 6. **Evaluation Instructions (Optional)**
Ask the agent to reflect, verify, or test its output.
> "Double-check that each recommendation aligns with the principles of GDPR."
> "Summarize how you arrived at these decisions in 100 words."

---

### 7. **Few-Shot or CoT Enhancer Blocks (Optional)**
Provide 1–3 examples for high-complexity prompts.

**Example:**
```
Input: Article about AI model bias in hiring platforms
Output: Summary + 2 case studies of real-world bias effects

Input: Annual water quality report
Output: Executive brief + risks table + compliance rating
```

---

## Full Example Prompt
```
You are a senior urban planner with expertise in disaster resilience and smart cities.

Your task is to analyze the attached flood risk data and propose a 5-year infrastructure plan for Jakarta.

Steps:
1. Identify key flood-prone zones using elevation + precipitation overlays.
2. Prioritize zones based on population density.
3. Recommend structural and policy interventions.
4. Assess environmental impact and funding constraints.

Constraints:
- Limit plan to 1000 words.
- Use only official government or NGO data.
- Output format: Markdown report with embedded table.

Evaluation:
Include a final paragraph explaining which zones have the highest urgency and why.
```

---

## Advanced Features

### Prompt Tuning Dimensions
- **Precision**: Increase or reduce verbosity.
- **Creativity**: Use language models with adjusted temperature.
- **Formality**: Inject brand-specific tone.
- **Technicality**: Add domain constraints (e.g., formulas, citations).

### Debugging Guidelines
- Inject known data and verify answers.
- Isolate one step of the chain to test.
- Split prompt into modules (input, logic, output).

---

## Reuse Best Practices
- Store as parameterized templates with `[PLACEHOLDER]` fields.
- Version by domain and use-case: `golden_prompt_v3.4_finance.md`
- Track effectiveness across agents or deployments

---

## License
MIT License – Free to use, adapt, and improve.
Credit appreciated.
