# Multi-Agent Prompt Engineering Template (Comprehensive)

## Purpose
This template is designed for structuring collaborative prompt systems where **multiple specialized AI agents** work in sequence, parallel, or loops to solve complex tasks.

Multi-agent prompt engineering is critical when:
- The problem space is modular or multi-domain.
- Task decomposition enables parallelism.
- Role separation improves accuracy or maintainability.

Examples include multi-agent RAG pipelines, software architecture design, multi-step content workflows, and autonomous operations.

---

## Template Architecture

### 1. **Mission Definition**
Clearly state the overall objective of the entire agent system.

**Example:**
> Design and validate an AI-powered travel itinerary system using Retrieval-Augmented Generation (RAG), optimized for real-time updates and personalization.

---

### 2. **Agent Design & Role Mapping**
Break the task into agent functions. Use role-based specialization.

| Agent | Role | Responsibilities |
|-------|------|-------------------|
| Supervisor | Overseer | Delegates tasks, ensures order and coordination |
| Retrieval | Researcher | Collects contextual information (e.g. documents, APIs) |
| Planner | Architect | Designs strategies, workflows, or systems |
| Validator | Auditor | Reviews output against requirements |
| UX Agent | Designer | Formats output for user delivery (markdown, GUI, etc.) |

Include fallback or watchdog agents if needed for high-stakes systems.

---

### 3. **Communication Protocol**
Define how agents share knowledge or output.

**Formats:**
- JSON payloads with explicit schema
- Markdown summaries with `@tags`
- Context window handoff with labeled memory
- Table-passing or chat threading

**JSON Communication Example:**
```json
{
  "task_id": "rag-0017",
  "from_agent": "retrieval",
  "to_agent": "planner",
  "context": "Top 5 activities in Kyoto during cherry blossom season",
  "timestamp": "2025-04-21T14:00Z"
}
```

---

### 4. **Task Orchestration Logic**
Define the flow of task execution:
- **Linear**: Supervisor → Retrieval → Planner → UX
- **Parallel**: Retrieval & Planner run concurrently
- **Looped**: Validator sends feedback to Planner, repeat until approved

Use a logic graph or numbered steps in production systems.

**Example:**
```
Step 1: Supervisor initializes task
Step 2: Retrieval agent collects context
Step 3: Planner builds solution
Step 4: Validator confirms accuracy
Step 5: UX agent formats result
```

---

### 5. **Agent Constraints and Tools**
Define capabilities, allowed tools, and boundaries for each agent.

**Example:**
- Retrieval agent may use Wikipedia + OpenWeather API only
- Planner must follow specific business logic
- UX agent must format output in Tailwind CSS or Markdown

---

### 6. **Final Output Schema**
Define what a complete, successful output looks like.
- Format: Markdown + JSON + PDF (optional)
- Sections: Executive Summary, Workflow, Raw Logs, Feedback

**Example:**
```markdown
## Executive Summary
A 5-day itinerary was created for Kyoto including cherry blossom viewing, tea ceremony, and local cuisine.

## JSON Log
```
```json
{
  "summary": "5-day itinerary",
  "key_locations": ["Maruyama Park", "Kiyomizu-dera"],
  "weather_dependency": true
}
```

---

## Prompt Example
```
Mission: Design a personalized travel plan for a solo traveler to Kyoto.

Agents:
- Supervisor: Oversees task distribution
- Retrieval: Gathers latest events, weather, crowd forecasts
- Planner: Combines data into a day-by-day itinerary
- Validator: Cross-checks for feasibility and local timing
- UX Agent: Outputs as Markdown + JSON

Constraints:
- Assume travel dates: March 28 – April 3
- Traveler prefers quiet scenic locations and cultural activities
- Output format must include estimated time per activity

Communication: Use JSON blocks with embedded notes per agent
```

---

## Advanced Features
- **Memory Pools**: Each agent stores state in shared vector memory (e.g. Pinecone)
- **Routing Logic**: Use logic trees or LLM routers to assign agent chains
- **Debugging Layer**: Meta-agent reviews coordination quality
- **Adaptive Loops**: Agents retry or expand tasks based on goal deltas

---

## Versioning and Deployment Notes
- Maintain prompt versions for each agent (e.g. `planner_v3.1.md`)
- Align token limits across agents for reliable output
- Include latency tracking if deployed live

---

## License
MIT License. Collaboration templates are open-source and extendable. Contributions welcome.
