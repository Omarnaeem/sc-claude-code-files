# The 3-Month AI PM Roadmap (2025 Edition)
**From Cloud Infrastructure to Shipping AI Features**

> For product managers with cloud/data platform experience transitioning to AI product work
>
> Time commitment: 10-15 hours/week over 12 weeks
>
> Focus: Modern 2025 skills that ship features at Netflix, Google, Anthropic—not academic theory

---

## Executive Summary

**Your Advantage**: You already understand infrastructure, data pipelines, scalability trade-offs, and technical collaboration. This roadmap builds on that foundation.

**Your Gaps**: AI product management requires understanding model behavior, evaluation frameworks, prompt engineering, and agentic systems—not coding ML models, but knowing enough to make product decisions.

**The Shift**: From "build it and scale it" to "does it work, is it safe, and will it stay working?" AI products degrade over time, hallucinate, and need continuous evaluation. Your cloud ops mindset will help, but the mental model is different.

**What Success Looks Like**: In 12 weeks, you'll ship a working AI prototype, design evaluation frameworks for production features, and architect multi-agent systems using modern tooling. You won't be an ML engineer, but you'll speak their language and make better product decisions.

---

## Week-by-Week Roadmap

### **MONTH 1: FOUNDATIONS & PROTOTYPING**

#### **Week 1: AI/LLM Fundamentals (The PM Lens)**

**Core Concept**: What PMs need to know vs. what ML engineers know

**Time Allocation** (12 hours):
- Anthropic's Claude documentation (2 hours) - Read "How Claude Works" and "Prompt Engineering Guide"
- OpenAI's GPT-4 model card & system card (2 hours) - Understand capabilities, limitations, safety
- Lenny's AI PM Guide (3 hours) - [lennysnewsletter.com/ai-prototyping-for-product](https://www.lennysnewsletter.com/p/a-guide-to-ai-prototyping-for-product)
- Hands-on: ChatGPT, Claude, Gemini experimentation (5 hours) - Test same prompts across models

**Hands-On Exercise**:
Build a "model comparison matrix" for a specific use case (e.g., customer support):
- Test 5+ prompts across ChatGPT, Claude, Gemini
- Document: response quality, latency, hallucinations, tone
- Make a build/buy recommendation with reasoning

**PM Decision This Enables**: "Should we use GPT-4, Claude Opus, or fine-tune an open-source model for our use case?"

**Cloud/Data Context**: Your understanding of API latency, rate limits, and service reliability maps directly to LLM endpoint management. Model inference is like a stateless microservice with variable latency.

**Must Know**:
- LLM basics (tokens, context windows, temperature, top-p)
- Difference between base models, instruction-tuned, RLHF
- Why models hallucinate and what that means for products
- Cost structure (input tokens vs output tokens)

**Nice to Have**:
- Transformer architecture details
- Training process specifics

---

#### **Week 2: First No-Code Prototype**

**Core Concept**: PMs can build now, not just spec

**Time Allocation** (14 hours):
- v0.dev tutorial + build 2 UI components (4 hours)
- Bolt.new tutorial + build a simple full-stack app (5 hours)
- Replit Agent exploration (2 hours)
- Read: "AI Prototyping for PMs" deep dive (3 hours)

**Hands-On Exercise**:
Pick ONE real problem from your current/past product work:
- Build a prototype in Bolt.new or v0.dev (6-8 hours)
- Document: what worked, what broke, where you needed human intervention
- Share with 3 people for feedback

**PM Decision This Enables**: "Is this AI feature feasible? Can I validate user interest before writing a PRD?"

**Why This Matters**: You can now test ideas in hours instead of waiting weeks for engineering time. Prototypes accelerate stakeholder alignment and de-risk roadmap commitments.

**Tool Comparison**:
- **v0.dev**: Best for React/Next.js UI components, clean design, Vercel integration
- **Bolt.new**: Best for full-stack MVPs with backend logic, fastest scaffolding
- **Replit Agent**: Best for quick deployment with hosting included
- **Cursor**: Best for technical PMs who code, requires development knowledge

**Cloud/Data Context**: These tools generate code that deploys to Vercel, Netlify, or Replit infrastructure. Your cloud knowledge helps you evaluate hosting costs, scalability limits, and production readiness.

---

#### **Week 3: Data Pipelines & Quality for AI**

**Core Concept**: Garbage in, garbage out—at scale

**Time Allocation** (12 hours):
- Read: "Data Quality for ML" (Google ML Guide, 2 hours)
- AWS SageMaker Data Wrangler tutorial (3 hours)
- Hands-on: Build a data quality scorecard template (4 hours)
- Case study: Analyze a public AI failure caused by data issues (3 hours)

**Hands-On Exercise**:
Create a "Data Quality Checklist" for AI features:
- Schema validation rules
- Bias detection strategies
- Sampling strategies for training/eval
- Monitoring metrics (drift, distribution shifts)
- Version control for datasets

**PM Decision This Enables**: "Is our data good enough to train/fine-tune? What quality bar do we need?"

**Why This Matters**: 80% of AI PM work is data work. Models are commoditized; data moats are real. Your AWS/data platform experience is a massive advantage here.

**Cloud/Data Context**:
- **Your Advantage**: You understand S3, data lakes, ETL pipelines, data governance
- **New Skill**: Labeling workflows, active learning, data versioning for ML (like DVC, LakeFS)
- **Transfer**: Data quality monitoring → Model performance monitoring

**Must Know**:
- Training data vs. evaluation data vs. production data
- Class imbalance and why it breaks models
- Data drift and concept drift
- PII handling and data privacy for AI

**Nice to Have**:
- Specific labeling tools (Labelbox, Scale AI)
- Advanced sampling techniques

---

#### **Week 4: MILESTONE PROJECT 1 - Build AI Prototype**

**Deliverable**: Working interactive prototype + feasibility analysis

**Time Budget**: 8-10 hours

**Tools**: Bolt.new OR v0.dev (pick one)

**Project Scope**:
Build a customer-facing AI feature prototype that solves a real problem. Examples:
- AI-powered search for internal docs
- Smart categorization tool for support tickets
- Code review assistant for PRs
- Content generation tool for marketing

**Requirements**:
1. **Working prototype** (hosted, shareable link)
2. **Feasibility doc** (2 pages max):
   - Problem statement
   - Technical approach (which model, why)
   - Key risks (hallucinations, latency, cost)
   - Data requirements
   - Success metrics
   - Build vs. buy recommendation
3. **Demo video** (3 minutes, Loom)

**Success Criteria**:
- ✅ Prototype works for 3+ test cases
- ✅ You can explain technical trade-offs to engineering
- ✅ You've identified 2+ edge cases the prototype fails on
- ✅ You have a cost estimate ($/1000 requests)

**Common Pitfalls**:
- ❌ Building too much—keep scope tiny
- ❌ Ignoring edge cases and hallucinations
- ❌ Not testing with real users
- ❌ Overlooking cost at scale

**PM Skill Demonstrated**: Rapid validation, technical feasibility analysis, stakeholder communication

---

### **MONTH 2: PRODUCTION & EVALUATION**

#### **Week 5: Experimentation, A/B Testing, Metrics**

**Core Concept**: AI metrics ≠ traditional product metrics

**Time Allocation** (13 hours):
- Read: "A/B Testing for AI Features" (Booking.com, Airbnb blog posts, 3 hours)
- Study: Netflix experimentation platform architecture (2 hours)
- Hands-on: Design an A/B test for your Week 4 prototype (5 hours)
- Learn: Statistical significance for AI (3 hours)

**Hands-On Exercise**:
Design a full A/B test plan:
- **Hypothesis**: "AI-generated summaries increase task completion by 20%"
- **Metrics**:
  - Primary: Task completion rate
  - Secondary: Time to completion, user satisfaction (CSAT)
  - Guardrail: Accuracy (human eval), hallucination rate, cost per session
- **Sample size calculation**
- **Success criteria**
- **Rollback plan**

**PM Decision This Enables**: "Should we ship this AI feature? What's the impact? What could go wrong?"

**Why This Matters**: AI features have unique metrics: accuracy, hallucination rate, latency, cost per request. You need both traditional product metrics AND AI-specific guardrails.

**Cloud/Data Context**: Your experience with observability (CloudWatch, DataDog) transfers directly. AI monitoring adds model-specific metrics on top of infra metrics.

**Must Know**:
- How to measure AI quality (precision, recall, F1 for classification; BLEU/ROUGE for generation)
- Cost per request and how to set budgets
- Latency impact on UX
- When to use human eval vs. automated metrics

**AI-Specific Metrics Framework**:
```
1. Model Performance: Accuracy, precision, recall, F1
2. Generation Quality: BLEU, ROUGE, human preference score
3. Safety: Hallucination rate, toxicity score, PII leakage
4. Business Impact: Conversion, engagement, retention
5. Operational: Latency (p50, p99), cost/request, uptime
```

---

#### **Week 6: Advanced Prompt Engineering**

**Core Concept**: Prompt engineering is interface design for LLMs

**Time Allocation** (14 hours):
- Read: Anthropic's prompt engineering guide (3 hours)
- OpenAI's prompt engineering best practices (2 hours)
- Hands-on: PromptLayer tutorial (4 hours)
- Build: Versioned prompt library for your domain (5 hours)

**Hands-On Exercise**:
Create a "prompt engineering playbook" for your product area:
- 10+ production-quality prompts with versioning
- Few-shot examples for each use case
- System prompts with guardrails
- A/B test results (if available)
- Cost analysis per prompt variant

**Tools to Learn**:
- **PromptLayer**: Prompt versioning, A/B testing, analytics
- **LangSmith**: Debugging, tracing, evaluation
- **Helicone**: Observability and caching

**PM Decision This Enables**: "Which prompt variant should we ship? How do we manage prompt changes in production?"

**Why This Matters**: Prompts are your product's UI. A 10-word change can 2x accuracy or halve cost. PMs own this layer, not ML engineers.

**Advanced Techniques**:
- **Chain of Thought (CoT)**: "Let's think step by step" improves reasoning
- **Few-shot learning**: Provide 3-5 examples in the prompt
- **System prompts**: Define personality, guardrails, output format
- **Prompt chaining**: Break complex tasks into steps
- **Self-consistency**: Generate multiple answers, pick most common

**Production Best Practices**:
- Version all prompts in Git or a prompt management system
- A/B test prompt changes like code changes
- Monitor prompt performance over time (models change)
- Build fallback prompts for edge cases
- Budget tokens (context window is finite)

**Cloud/Data Context**: Prompt management is like API versioning. You need rollback capability, monitoring, and change management.

---

#### **Week 7: Ethics, Bias, and Safety**

**Core Concept**: Ship responsibly or don't ship at all

**Time Allocation** (11 hours):
- Read: Anthropic's Constitutional AI paper (summary, 2 hours)
- OpenAI's GPT-4 System Card (safety evaluations, 2 hours)
- Google's PAIR guidebook (fairness in ML, 3 hours)
- Case studies: AI failures (Tay, Amazon recruiting tool, 2 hours)
- Hands-on: Red-team your Week 4 prototype (2 hours)

**Hands-On Exercise**:
Conduct a "safety review" of your prototype:
1. **Bias audit**: Test with diverse inputs, look for demographic bias
2. **Red teaming**: Try to make it fail, hallucinate, leak data
3. **Safety scorecard**: Rate on fairness, transparency, privacy, security
4. **Mitigation plan**: Document risks and how you'd address them

**PM Decision This Enables**: "Is this feature safe to ship? What risks need mitigation?"

**Why This Matters**: You're accountable for AI harms, not just uptime. One viral failure can kill your product. PMs must be the ethical voice in the room.

**Key Areas**:
- **Bias**: Training data bias → model bias → user harm
- **Hallucinations**: Models confidently state false information
- **Privacy**: PII leakage, training data memorization
- **Security**: Prompt injection, jailbreaking, adversarial attacks
- **Transparency**: Explainability, user trust

**Frameworks**:
- **Microsoft's HAX Toolkit**: Human-AI experience design patterns
- **Google's PAIR**: People + AI Research guidelines
- **NIST AI Risk Management Framework**: Enterprise AI governance

**Must Know**:
- How to detect and mitigate bias in training data
- Red teaming techniques (prompt injection, jailbreaking)
- When to use human-in-the-loop vs. full automation
- Regulatory landscape (EU AI Act, California AI laws)

**Cloud/Data Context**: You understand SOC2, GDPR, data encryption. AI adds new compliance requirements (model transparency, explainability, bias audits).

---

#### **Week 8: MILESTONE PROJECT 2 - Evaluation Framework**

**Deliverable**: Evaluation dashboard + automated tests + vendor comparison

**Time Budget**: 8-10 hours

**Tools**: PromptLayer OR Langfuse + custom eval scripts

**Project Scope**:
Build a production-ready evaluation framework for an AI feature (use your Week 4 prototype or a new use case).

**Requirements**:

1. **Automated Eval Suite**:
   - 50+ test cases covering:
     - Happy path (30 cases)
     - Edge cases (10 cases)
     - Adversarial cases (10 cases)
   - Automated scoring (pass/fail, quality score 1-5)
   - Cost per test case

2. **Vendor Comparison**:
   - Test 3+ models (e.g., GPT-4, Claude Opus, Gemini Pro)
   - Metrics: accuracy, latency, cost, hallucination rate
   - Recommendation with trade-offs

3. **Dashboard**:
   - Use PromptLayer, Langfuse, or build custom (Streamlit)
   - Track: pass rate over time, cost trends, latency p99
   - Alerts for degradation

4. **Documentation**:
   - Eval methodology (how you score quality)
   - Test case library (versioned)
   - Playbook: "When to re-run evals" (model updates, data drift)

**Success Criteria**:
- ✅ Eval suite runs automatically (GitHub Actions or cron)
- ✅ You catch 3+ failure modes the model has
- ✅ You can defend your vendor choice with data
- ✅ Dashboard is shareable with stakeholders

**Common Pitfalls**:
- ❌ Test cases too narrow (not representative of production)
- ❌ No baseline (can't measure improvement)
- ❌ Ignoring cost (accuracy at 10x cost isn't a win)
- ❌ Manual eval only (doesn't scale)

**PM Skill Demonstrated**: Data-driven decision making, production readiness, vendor management

**Why This Matters**: This is the difference between hobbyist AI and production AI. At Netflix/Google/Anthropic, every model change goes through eval suites like this.

---

### **MONTH 3: AGENTIC AI & PRODUCTION READINESS**

#### **Week 9: Model Context Protocol (MCP) - The "USB-C for AI"**

**Core Concept**: MCP standardizes how AI connects to data and tools

**Time Allocation** (12 hours):
- Read: Anthropic's MCP announcement + docs (3 hours)
- Study: MCP specification (GitHub, 2 hours)
- Explore: MCP server examples (Claude Code, Zed, 3 hours)
- Hands-on: Set up an MCP server locally (4 hours)

**Hands-On Exercise**:
Build or configure an MCP server:
- Option A: Use an existing MCP server (filesystem, Postgres, Slack)
- Option B: Build a simple custom MCP server (e.g., connect to internal API)
- Test with Claude Desktop or compatible client
- Document: what data it exposes, what tools it provides

**PM Decision This Enables**: "Should we build custom integrations or use MCP-compatible connectors?"

**Why This Matters**: MCP is becoming the standard for AI-data integration. By 2026, most AI products will use MCP instead of custom APIs. Understanding MCP helps you architect future-proof systems.

**What is MCP?**:
- **Problem**: Every AI assistant needs custom connectors to every data source (N×M integration problem)
- **Solution**: One protocol for AI ↔ data/tools, like USB-C for peripherals
- **Adoption**: Anthropic (Claude), Google (Gemini), OpenAI support; 1000+ community servers by early 2025

**Key Components**:
1. **MCP Hosts**: AI applications (Claude, IDEs like Zed/Cursor)
2. **MCP Clients**: Code that connects to servers
3. **MCP Servers**: Expose data/tools via standard protocol
4. **Resources**: Data sources (files, DBs, APIs)
5. **Tools**: Actions the AI can take (search, write, execute)

**Use Cases**:
- Connect Claude to your company's internal docs
- Give AI access to CRM data (Salesforce, HubSpot)
- Enable AI to run database queries
- Integrate with dev tools (Git, Jira, Slack)

**PM Lens**:
- **Before MCP**: Build custom API for every AI integration → engineering bottleneck
- **With MCP**: Use standard protocol → plug-and-play integrations
- **Trade-off**: MCP is young (launched Nov 2024), ecosystem still maturing

**Cloud/Data Context**: MCP is like REST APIs or gRPC for AI. Your API design knowledge transfers. Security, rate limiting, auth patterns all apply.

**Must Know**:
- MCP architecture (host, client, server, resources, tools)
- How to evaluate MCP servers (security, performance)
- When to build custom vs. use existing MCP servers

**Nice to Have**:
- How to build an MCP server from scratch
- MCP protocol internals (JSON-RPC over stdio/HTTP)

---

#### **Week 10: Agentic AI Frameworks - Part 1**

**Core Concept**: Agents are LLMs + tools + memory + planning

**Time Allocation** (14 hours):
- Read: "What are AI agents?" (Anthropic, OpenAI blogs, 2 hours)
- LangChain tutorial: Build a simple agent (4 hours)
- LangGraph tutorial: Stateful agent workflows (4 hours)
- Study: Real agent examples (e.g., Devin, Claude Code, 2 hours)
- Hands-on: Build a tool-calling agent (2 hours)

**Hands-On Exercise**:
Build a "research agent" using LangChain or LangGraph:
- Takes a question as input
- Searches web (using tool/API)
- Reads top 3 results
- Synthesizes answer with citations
- Returns structured output

**PM Decision This Enables**: "Should we build an agentic feature? What's the architecture?"

**Why This Matters**: Agentic AI is the 2025-2026 frontier. Products like Claude Code, GitHub Copilot Workspace, and Devin are agents. PMs need to understand agent capabilities, limitations, and failure modes.

**Agent Anatomy**:
1. **LLM brain**: Reasoning and planning
2. **Tools**: Functions the agent can call (search, calculator, APIs)
3. **Memory**: Short-term (conversation) + long-term (knowledge base)
4. **Planning**: ReAct (Reason + Act), chain of thought
5. **Control flow**: When to stop, retry, escalate

**Frameworks Overview**:

**LangChain**:
- Most mature ecosystem
- Chain LLM calls with tools
- Supports multiple LLMs, vector DBs, tools
- Use for: Prototyping, RAG, simple agents

**LangGraph**:
- Stateful, graph-based workflows
- Cyclical flows (agent can loop, retry)
- Better for: Multi-step agents, conditional logic
- Production-ready (used at Anthropic)

**Key Concepts**:
- **Tools**: Functions the agent can call (defined via JSON schema)
- **ReAct prompting**: "Thought → Action → Observation" loop
- **Memory**: Conversation buffer, vector store, knowledge graph
- **Guardrails**: Max iterations, budget limits, human-in-the-loop

**Cloud/Data Context**: Agent orchestration is like workflow orchestration (Airflow, Step Functions). State management, error handling, retries, observability all apply.

---

#### **Week 11: Agentic AI Frameworks - Part 2 + Production Readiness**

**Core Concept**: Multi-agent systems and collaboration

**Time Allocation** (13 hours):
- CrewAI tutorial: Role-based agents (4 hours)
- AutoGen tutorial: Multi-agent conversations (4 hours)
- Study: Production agent patterns (2 hours)
- Read: "Technical collaboration for AI PMs" (2 hours)
- Hands-on: Design a multi-agent system (1 hour)

**Hands-On Exercise**:
Design (on paper or Figma) a multi-agent system for a real use case:
- Example: "Content creation pipeline" with agents for research, writing, editing, fact-checking
- Define: Agent roles, tools, handoffs, escalation paths
- Document: Failure modes, cost estimate, success metrics

**Frameworks Deep Dive**:

**CrewAI**:
- Role-based team of agents
- Each agent has role, goal, backstory
- Agents collaborate on tasks
- Use for: Simulating human teams (research + writing + editing)

**AutoGen (Microsoft)**:
- Conversation-first framework
- Agents chat to solve problems
- Supports human-in-the-loop
- Production use: Novo Nordisk data science

**Production Readiness Checklist**:
- [ ] Observability: Trace every agent action (LangSmith, Langfuse)
- [ ] Cost controls: Budget limits, circuit breakers
- [ ] Latency: Async execution, streaming responses
- [ ] Error handling: Retries, fallbacks, graceful degradation
- [ ] Safety: Guardrails, human review for high-stakes actions
- [ ] Evaluation: Automated tests for agent workflows

**Technical Collaboration**:
- **With ML engineers**: You define success metrics, they optimize models
- **With data engineers**: You specify data requirements, they build pipelines
- **With platform engineers**: You set latency/cost SLAs, they architect infra
- **With design**: You validate UX patterns for AI uncertainty (loading states, confidence scores)

**PM Skills**:
- Writing technical specs for AI features
- Reviewing model eval results with data scientists
- Scoping MVPs that balance capability and feasibility
- Communicating AI limitations to stakeholders

**Cloud/Data Context**: Your experience with SLAs, incident response, on-call rotations applies. Add: model degradation alerts, cost spike alerts, quality metric drops.

---

#### **Week 12: MILESTONE PROJECT 3 - Multi-Agent System Design**

**Deliverable**: Agent architecture + MCP integration plan + PRD

**Time Budget**: 10-12 hours

**Tools**: LangChain OR CrewAI + MCP concepts + Figma/Miro for architecture

**Project Scope**:
Design a production-ready agentic AI feature for a real product. Examples:
- Customer support agent (triage → research → draft response → human review)
- Code review agent (analyze PR → run tests → suggest fixes → post comments)
- Content pipeline (research → write → edit → fact-check → publish)

**Requirements**:

1. **Agent Architecture Diagram**:
   - Agent roles and responsibilities
   - Tools each agent uses
   - Data sources (MCP servers or APIs)
   - Handoff points between agents
   - Human-in-the-loop checkpoints
   - Error handling and escalation paths

2. **MCP Integration Plan**:
   - Which data sources need MCP servers?
   - Existing MCP servers to use (e.g., GitHub, Slack, PostgreSQL)
   - Custom MCP servers to build
   - Security and access control
   - Cost estimate for MCP operations

3. **PRD (Product Requirements Document)**:
   - Problem statement and user stories
   - Success metrics (product + AI-specific)
   - Technical approach (which framework, which models)
   - Risks and mitigations
   - MVP scope (what ships first, what's v2)
   - Cost model ($/request, $/user)
   - Timeline and dependencies

4. **Evaluation Plan**:
   - How to measure agent success
   - Test cases for agent workflows
   - Guardrails and safety measures
   - Rollback strategy

**Success Criteria**:
- ✅ Architecture is technically feasible (validated with an engineer)
- ✅ MCP integration makes sense (not over-engineered)
- ✅ PRD is clear enough for eng team to scope
- ✅ You've identified 3+ failure modes and mitigations
- ✅ Cost model is realistic (benchmarked against real pricing)

**Common Pitfalls**:
- ❌ Too many agents (start with 1-2)
- ❌ Ignoring failure modes (agents will fail often)
- ❌ No human-in-the-loop (full automation is risky)
- ❌ Underestimating cost (agent loops are expensive)

**PM Skill Demonstrated**: System design, cross-functional collaboration, strategic thinking, risk management

**Why This Matters**: This is the capstone. You're now thinking like an AI PM at a top company. You can scope, design, and ship agentic AI features.

---

## Success Milestones & Check-ins

### **Week 4 Check-in: Can you prototype?**
- ✅ Built a working AI feature in Bolt/v0
- ✅ Can explain technical trade-offs (model choice, latency, cost)
- ✅ Identified edge cases and failure modes
- ✅ Estimated cost at scale

**If struggling**: Spend more time with no-code tools. Watch tutorial videos. Build smaller scopes.

---

### **Week 8 Check-in: Can you evaluate?**
- ✅ Built automated eval suite with 50+ test cases
- ✅ Compared 3+ models with data
- ✅ Can defend vendor choice to stakeholders
- ✅ Dashboard tracks performance over time

**If struggling**: Simplify eval metrics. Start with pass/fail, then add quality scoring. Focus on automation.

---

### **Week 12 Check-in: Can you ship?**
- ✅ Designed a production-ready agentic feature
- ✅ PRD is clear and scoped
- ✅ Integrated MCP for data access
- ✅ Identified risks and mitigations
- ✅ Can communicate technical architecture to eng team

**If struggling**: Narrow scope. Start with single-agent systems. Get feedback from engineers early.

---

## Tool Recommendations by Category

### **Prototyping (Learn by Building)**

| Tool | Best For | Skill Level | Cost | When to Use |
|------|----------|-------------|------|-------------|
| **v0.dev** | React/Next.js UI components | Low | Free tier, $20/mo pro | Front-end prototypes, design validation |
| **Bolt.new** | Full-stack MVPs with backend | Low | Free tier, $20/mo | Quick full-stack demos, Stripe integration |
| **Replit Agent** | Deployed apps with hosting | Low-Medium | Free tier, $20/mo | Need live URL immediately |
| **Cursor** | AI-powered coding (IDE) | Medium-High | $20/mo | Technical PMs who code |
| **Claude Code** | Terminal-based dev agent | Medium | Included with Claude Pro | Command-line workflows, scripting |

**PM Use Cases**:
- **Week 1-2**: Validate feature ideas before PRD
- **Before roadmap planning**: Test feasibility of AI features
- **During discovery**: Build throwaway prototypes for user testing
- **For stakeholders**: Demo concepts in leadership reviews

---

### **Evaluation & Testing**

| Tool | Best For | Skill Level | Cost | When to Use |
|------|----------|-------------|------|-------------|
| **PromptLayer** | Prompt management, versioning | Low-Medium | Free tier, $99/mo team | Production prompt tracking, A/B tests |
| **Langfuse** | LLM observability, tracing | Medium | Open-source (self-host) or cloud | Production monitoring, debugging |
| **Phoenix (Arize)** | Eval + tracing | Medium | Open-source | Experimentation, troubleshooting |
| **LangSmith** | Debugging, LangChain tracing | Medium | Free tier, $39/mo | If using LangChain/LangGraph |
| **W&B (Weights & Biases)** | Experiment tracking | Medium-High | Free tier, enterprise | A/B tests, model comparisons |
| **Custom evals** | Your specific use case | High | Free (DIY) | Always (no tool fits all) |

**PM Use Cases**:
- **Before launch**: Build eval suite for new AI features
- **Post-launch**: Monitor quality degradation over time
- **Model updates**: Test new models/prompts before rollout
- **Vendor selection**: Compare OpenAI vs Anthropic vs Google

**Must-Have Setup** (by Week 8):
1. Automated eval suite (50+ test cases)
2. Dashboard for key metrics (Langfuse or PromptLayer)
3. Alerts for quality drops
4. Cost tracking per feature

---

### **Agentic AI Frameworks**

| Framework | Best For | Complexity | When to Use |
|-----------|----------|------------|-------------|
| **LangChain** | RAG, simple agents, prototyping | Medium | General-purpose AI apps |
| **LangGraph** | Stateful workflows, multi-step agents | Medium-High | Production agents with loops |
| **CrewAI** | Role-based multi-agent teams | Medium | Simulating human teams |
| **AutoGen** | Conversational multi-agent | High | Research, complex collaboration |
| **OpenAI Agents SDK** | If using OpenAI exclusively | Low-Medium | Simple agents, OpenAI ecosystem |

**PM Decision Framework**:
- **Single agent + tools**: LangChain or OpenAI Agents SDK
- **Multi-step workflow**: LangGraph
- **Team of agents**: CrewAI or AutoGen
- **Need to ship fast**: Start with LangChain, migrate to LangGraph for production

**Cloud/Data Context**: These frameworks are like orchestrators (Airflow, Step Functions). Choose based on state management needs, not hype.

---

### **MCP (Model Context Protocol)**

**Status**: Rapidly growing ecosystem (launched Nov 2024, 1000+ servers by Feb 2025)

**Adoption**:
- ✅ Anthropic (Claude Desktop, Claude Code)
- ✅ Google (Gemini, announced April 2025)
- ✅ OpenAI (in progress)
- ✅ IDEs (Zed, Cursor, Sourcegraph)

**Popular MCP Servers**:
- **Filesystem**: Access local files
- **PostgreSQL**: Query databases
- **GitHub**: Read repos, create issues, review PRs
- **Slack**: Read/send messages
- **Google Drive**: Access docs
- **Custom**: Build your own (Python, TypeScript, Go)

**PM Lens**:
- **When to use**: Need AI to access data sources (DBs, APIs, docs)
- **When to wait**: Need complex auth, very high throughput (MCP still maturing)
- **Strategic bet**: By 2026, MCP will be standard—learn it now

**Resources**:
- Anthropic MCP docs: https://docs.anthropic.com/en/docs/agents-and-tools/mcp
- MCP specification: https://github.com/anthropics/mcp
- Community servers: https://github.com/anthropics/mcp-servers

---

## Common Traps to Avoid

Based on coaching 100+ PMs transitioning to AI:

### **Trap 1: Treating AI Like Deterministic Software**

**The Mistake**: Expecting AI to work like traditional code. Writing specs like "The feature will always X."

**Why It Fails**: LLMs are probabilistic. Same input → different outputs. Models hallucinate. Performance degrades over time.

**The Fix**:
- Write specs with error budgets: "95% accuracy on eval set"
- Build eval suites, not test suites (quality scoring, not pass/fail)
- Plan for failure modes (fallbacks, human-in-the-loop)
- Monitor production continuously (model drift is real)

**Your Cloud Advantage**: You understand eventual consistency, retries, circuit breakers. Apply those mental models to AI.

---

### **Trap 2: Falling in Love with the Technology**

**The Mistake**: "We should use multi-agent RAG with fine-tuned LLaMA because it's cool."

**Why It Fails**: Complexity for complexity's sake. Overengineering. Slow shipping.

**The Fix**:
- Start with the simplest solution (GPT-4 API call with good prompts)
- Upgrade only when you hit limits (cost, latency, accuracy)
- Build vs buy: API > fine-tuning > training from scratch
- Your job is solving user problems, not publishing papers

**PM Principle**: Ship the boring solution that works. Iterate from there.

---

### **Trap 3: Underestimating Data Work**

**The Mistake**: "We'll just use GPT-4, we don't need data."

**Why It Fails**: Models are commoditized. Data moats are real. Garbage in, garbage out.

**The Fix**:
- Spend 50% of time on data (quality, labeling, versioning)
- Build eval datasets before building features
- Invest in data pipelines (your cloud background helps here)
- Monitor data drift (distribution shifts break models)

**Your Cloud Advantage**: You understand data pipelines, ETL, data governance. That's 70% of AI PM work.

---

### **Trap 4: Shipping Without Evals**

**The Mistake**: "It works in my testing, ship it."

**Why It Fails**: Your 10 test cases don't represent production. Models fail in unexpected ways.

**The Fix**:
- Build eval suite before building the feature
- 50+ test cases minimum (happy path, edge cases, adversarial)
- Automate evals (CI/CD for AI)
- Re-run evals on every model/prompt change

**PM Standard**: No eval suite = not ready to ship. Non-negotiable.

---

### **Trap 5: Ignoring Cost**

**The Mistake**: "GPT-4 is only $0.03 per 1K tokens, NBD."

**Why It Fails**: At scale, costs explode. Agent loops can burn $1+ per request.

**The Fix**:
- Calculate cost per request, per user, per month
- Set budgets and alerts
- Optimize prompts for cost (shorter prompts, caching)
- Consider cheaper models for simple tasks (GPT-3.5, Haiku)

**PM Discipline**: Every feature needs a cost model. Track cost/value ratio.

---

### **Trap 6: Building Agents Too Early**

**The Mistake**: "Let's build a multi-agent system for v1."

**Why It Fails**: Agents are complex, expensive, error-prone. Hard to debug.

**The Fix**:
- Start with single LLM call
- Add tools only when needed
- Single agent before multi-agent
- Statefulness only when necessary

**PM Ladder**:
1. Simple prompt → LLM → output
2. Prompt + few-shot examples
3. Single agent with tools
4. Stateful agent (LangGraph)
5. Multi-agent (CrewAI/AutoGen)

Start at step 1. Move up only when you hit limits.

---

### **Trap 7: No Human-in-the-Loop**

**The Mistake**: "Fully autonomous AI, no human needed."

**Why It Fails**: AI makes mistakes. High-stakes errors (legal, medical, financial) need human oversight.

**The Fix**:
- Identify high-risk actions (delete data, send email, financial transactions)
- Require human approval for high-stakes
- Start with AI-assisted (human decides), not AI-autonomous
- Gradually increase automation as trust builds

**PM Framework**:
- **Low stakes** (recommendations, summaries): Full automation OK
- **Medium stakes** (draft content, triage): AI suggests, human approves
- **High stakes** (legal, medical, finance): Human decides, AI assists

---

## Case Studies to Study (2024-2025 Products)

Learn from what's actually shipping:

### **1. ChatGPT Search (OpenAI, 2024)**
**What they shipped**: Real-time web search integrated into ChatGPT

**PM Lessons**:
- Launched with partnerships (AP, Reuters) for quality
- Clear UX for citations (builds trust)
- Separate product tier (SearchGPT → ChatGPT integration)

**Study**:
- How they handle recency (breaking news)
- Citation UX patterns
- Search vs. chat modality

---

### **2. Claude Code (Anthropic, 2025)**
**What they shipped**: Terminal-based coding agent, $500M ARR in 2 months

**PM Lessons**:
- Fastest-growing product ever (per Anthropic)
- Built on Claude Opus 4 (long context, agentic capabilities)
- MCP integration for tool access

**Study**:
- Agent architecture (read files → edit → run tests)
- How they handle failure modes (infinite loops, bad code)
- Pricing model (included with Claude Pro)

---

### **3. GitHub Copilot (Microsoft, 2024-2025 evolution)**
**What they shipped**: Multi-model support, Copilot Workspace (agentic)

**PM Lessons**:
- Shifted from single model (OpenAI) to multi-model (Gemini, Claude, OpenAI)
- MCP adoption (deprecating Copilot Extensions)
- Workspace = agent that plans → implements → tests

**Study**:
- How they manage model switching (UX, cost)
- IDE integration patterns
- Copilot Chat vs. Copilot Workspace (scoped vs. agentic)

---

### **4. Perplexity AI (2024-2025)**
**What they shipped**: AI-native search with citations, Pro Search (multi-step reasoning)

**PM Lessons**:
- Citation-first UX (transparency builds trust)
- Tiered features (free vs Pro)
- Pro Search = agentic reasoning for complex queries

**Study**:
- How they differentiate from ChatGPT Search
- Pro Search prompt patterns (likely multi-step ReAct)
- Business model (freemium → subscriptions)

---

### **5. Notion AI (Notion, 2023-2025)**
**What they shipped**: AI writing assistant deeply integrated into workspace

**PM Lessons**:
- Contextual AI (uses your workspace data)
- Simple features shipped fast (summarize, rewrite, generate)
- Gradual rollout (learn from usage)

**Study**:
- Integration patterns (inline, sidebar, slash commands)
- How they handle privacy (your data stays yours)
- Feature prioritization (what shipped first vs. later)

---

### **6. Netflix AI (2024-2025)**
**What they shipped**: Generative AI for VFX, content search, ad-tech

**PM Lessons**:
- AI across production (on-screen footage, VFX acceleration)
- AI for platform (search, recommendations, ads)
- "All in on AI" strategy (CEO quote)

**Study**:
- How they use AI for internal tools (production workflows)
- Experimentation culture (A/B testing AI features)
- Multi-cloud AI strategy (AWS, Google, Azure)

---

### **7. Anthropic Claude (2024-2025)**
**What they shipped**: Claude Opus 4, Sonnet 4.5, extended context (200K+ tokens), agentic capabilities

**PM Lessons**:
- Model tiering (Haiku = fast/cheap, Sonnet = balanced, Opus = powerful)
- Agentic features (extended autonomy, tool use)
- Safety-first (Constitutional AI)

**Study**:
- How they communicate model capabilities (model cards)
- Pricing strategy (Opus is premium)
- Enterprise features (Claude for Work)

---

## What Good Enough Looks Like

You're not becoming an ML engineer. Here's the bar for AI PMs:

### **Good Enough: Technical Understanding**

✅ **You can**:
- Explain how LLMs work (at a high level) to non-technical stakeholders
- Distinguish GPT-4 vs Claude vs Gemini capabilities
- Read a model card and understand trade-offs
- Estimate cost per request given token counts
- Identify when to use GPT-4 vs GPT-3.5 vs fine-tuned model

❌ **You don't need to**:
- Code a transformer from scratch
- Understand backpropagation math
- Train models yourself
- Optimize CUDA kernels

---

### **Good Enough: Prompt Engineering**

✅ **You can**:
- Write production-quality prompts with examples and guardrails
- A/B test prompt variants and pick winners
- Version prompts in a management system
- Debug why a prompt fails on edge cases

❌ **You don't need to**:
- Become a prompt engineering researcher
- Publish papers on prompting techniques
- Memorize every prompting framework

---

### **Good Enough: Evaluation**

✅ **You can**:
- Build automated eval suites with 50+ test cases
- Track metrics over time (accuracy, cost, latency)
- Make go/no-go decisions based on eval results
- Explain eval methodology to stakeholders

❌ **You don't need to**:
- Design novel evaluation metrics
- Build custom eval frameworks from scratch
- Run academic-level benchmarks

---

### **Good Enough: Agentic AI**

✅ **You can**:
- Design agent architectures (roles, tools, handoffs)
- Choose the right framework (LangChain vs CrewAI)
- Identify failure modes and mitigations
- Write PRDs for agentic features

❌ **You don't need to**:
- Implement agents from scratch
- Contribute to LangChain codebase
- Research novel agent algorithms

---

### **Good Enough: Data & MLOps**

✅ **You can**:
- Define data quality requirements
- Design labeling workflows
- Understand data drift and how to monitor it
- Collaborate with data engineers on pipelines

❌ **You don't need to**:
- Build ETL pipelines yourself
- Manage Kubernetes clusters for ML
- Optimize model serving infrastructure

---

## Your Cloud/Infra PM Superpowers

You have hidden advantages. Use them:

### **1. Infrastructure Thinking**
- **Transfers**: SLAs, latency budgets, cost optimization, capacity planning
- **AI Application**: Model inference SLAs, token budgets, cost per request, rate limits

### **2. Data Pipeline Experience**
- **Transfers**: ETL, data quality, schema validation, versioning
- **AI Application**: Training data pipelines, eval datasets, data drift monitoring

### **3. Observability Mindset**
- **Transfers**: Metrics, logging, alerting, dashboards (CloudWatch, DataDog)
- **AI Application**: Model performance metrics, LLM tracing (LangSmith, Langfuse)

### **4. API Design**
- **Transfers**: REST, GraphQL, versioning, rate limiting, auth
- **AI Application**: LLM API wrappers, MCP server design, tool schemas

### **5. Cost Management**
- **Transfers**: AWS cost optimization, reserved instances, spot pricing
- **AI Application**: Token optimization, model selection, caching, batch processing

### **6. Reliability Engineering**
- **Transfers**: Retries, circuit breakers, graceful degradation, failovers
- **AI Application**: Prompt fallbacks, model fallbacks, human-in-the-loop escalation

### **7. Security & Compliance**
- **Transfers**: SOC2, GDPR, encryption, access control
- **AI Application**: PII handling, data privacy, model security, prompt injection defense

---

## Final Thoughts: From Cloud PM to AI PM

**What Changes**:
- **Deterministic → Probabilistic**: Software has bugs; AI has failure rates
- **Stable → Degrading**: Code doesn't rot; models drift
- **Test Suites → Eval Suites**: Pass/fail → quality scoring
- **Debugging → Red Teaming**: Stack traces → adversarial testing

**What Stays the Same**:
- Solve user problems, not technology problems
- Ship iteratively, measure impact, improve
- Collaborate with engineers, designers, stakeholders
- Balance feasibility, desirability, viability

**Your Edge**:
- You understand infrastructure, data, and scale
- You know how to ship production systems
- You can talk to engineers and translate for business
- You have experience with complex technical trade-offs

**The Opportunity**:
By 2026, all PMs will be AI PMs. You're ahead of the curve.

---

## Next Steps After Week 12

You've completed the roadmap. Here's how to keep growing:

### **Week 13-16: Specialize**

Pick one area to go deeper:
- **Option A**: Agentic AI (build a real agent, ship to production)
- **Option B**: Evaluation (become the eval expert on your team)
- **Option C**: MCP (build custom MCP servers for your company)

### **Week 17-20: Ship Something Real**

- Propose an AI feature at your company
- Write a PRD using your Week 12 skills
- Build a prototype in Bolt/v0
- Present to stakeholders with eval results

### **Week 21-24: Join the Community**

- Share your learnings (blog, LinkedIn, Twitter)
- Contribute to open source (MCP servers, LangChain tools)
- Join AI PM communities (Lenny's, Product School)

### **Continuous Learning**

- **Weekly**: Try new AI products, deconstruct what they ship
- **Monthly**: Read AI PM case studies (Lenny's Newsletter, First Round Review)
- **Quarterly**: Re-run evals on your projects (models improve, your bar should rise)

---

## Resources & Links

### **Essential Reading**

- **Anthropic Docs**: https://docs.anthropic.com (prompt engineering, MCP, Claude API)
- **OpenAI Cookbook**: https://cookbook.openai.com (GPT-4 guides, prompt examples)
- **Lenny's AI PM Guide**: https://www.lennysnewsletter.com/p/a-guide-to-ai-prototyping-for-product
- **Google PAIR**: https://pair.withgoogle.com (Human-AI interaction patterns)

### **Prototyping Tools**

- **v0.dev**: https://v0.dev
- **Bolt.new**: https://bolt.new
- **Replit**: https://replit.com
- **Cursor**: https://cursor.com

### **Evaluation Platforms**

- **PromptLayer**: https://promptlayer.com
- **Langfuse**: https://langfuse.com
- **Phoenix (Arize)**: https://phoenix.arize.com
- **LangSmith**: https://smith.langchain.com

### **Agentic AI Frameworks**

- **LangChain**: https://langchain.com
- **LangGraph**: https://langchain-ai.github.io/langgraph
- **CrewAI**: https://crewai.com
- **AutoGen**: https://microsoft.github.io/autogen

### **MCP Resources**

- **MCP Docs**: https://docs.anthropic.com/en/docs/agents-and-tools/mcp
- **MCP GitHub**: https://github.com/anthropics/mcp
- **MCP Servers**: https://github.com/anthropics/mcp-servers

### **Communities**

- **Lenny's Newsletter**: https://www.lennysnewsletter.com
- **Product School**: https://productschool.com
- **AI PM Discord/Slack**: (Search for latest communities)

---

**Good luck. Ship something.**

---

*Roadmap last updated: November 2025*
*For updates and feedback: This roadmap reflects 2025 tooling and practices.*
