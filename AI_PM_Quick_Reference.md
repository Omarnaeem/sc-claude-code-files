# AI PM Quick Reference Guide (2025)

**Companion to the 3-Month Roadmap**

---

## Weekly Time Commitment Breakdown

| Week | Focus Area | Hours | Key Deliverable |
|------|-----------|-------|-----------------|
| 1 | LLM Fundamentals | 12 | Model comparison matrix |
| 2 | No-Code Prototyping | 14 | Working prototype |
| 3 | Data Quality | 12 | Data quality checklist |
| **4** | **PROJECT 1** | **8-10** | **AI prototype + feasibility doc** |
| 5 | Experimentation & Metrics | 13 | A/B test plan |
| 6 | Prompt Engineering | 14 | Prompt library |
| 7 | Ethics & Safety | 11 | Safety review |
| **8** | **PROJECT 2** | **8-10** | **Evaluation framework + dashboard** |
| 9 | Model Context Protocol | 12 | MCP server setup |
| 10 | Agentic AI - Part 1 | 14 | Research agent |
| 11 | Agentic AI - Part 2 | 13 | Multi-agent design |
| **12** | **PROJECT 3** | **10-12** | **Agent architecture + PRD** |

**Total**: 141-151 hours over 12 weeks = ~12 hours/week average

---

## The AI PM Tech Stack (2025)

### Prototyping Layer
```
Purpose: Build demos in hours, validate ideas before PRDs

v0.dev          → UI components, React/Next.js
Bolt.new        → Full-stack MVPs with backend
Replit Agent    → Quick deployment with hosting
Cursor          → For technical PMs who code

When to use: Weeks 1-4, ongoing for feature validation
```

### Evaluation Layer
```
Purpose: Make data-driven decisions, production readiness

PromptLayer     → Prompt versioning, A/B testing
Langfuse        → LLM observability, monitoring
Phoenix (Arize) → Eval + tracing, debugging
LangSmith       → If using LangChain ecosystem
Custom Evals    → Always needed for your specific use case

When to use: Weeks 6-8, required before any production launch
```

### Agentic Layer
```
Purpose: Build autonomous AI systems with tools and memory

LangChain       → General-purpose, RAG, simple agents
LangGraph       → Stateful workflows, production agents
CrewAI          → Role-based multi-agent teams
AutoGen         → Conversational multi-agent (Microsoft)

When to use: Weeks 10-12, for advanced AI features
```

### Integration Layer
```
Purpose: Connect AI to data sources and tools

MCP (Model Context Protocol) → The "USB-C for AI"
- Standard protocol for AI ↔ data/tools
- 1000+ community servers (GitHub, Slack, PostgreSQL, etc.)
- Adopted by Anthropic, Google, OpenAI

When to use: Weeks 9-12, planning future integrations
```

---

## PM vs ML Engineer: Who Does What?

| Responsibility | PM Owns | ML Engineer Owns |
|----------------|---------|------------------|
| **Define success metrics** | ✅ | Helps advise |
| **Choose eval criteria** | ✅ | Implements |
| **Write prompts** | ✅ | Reviews |
| **Select model vendor** | ✅ (with eng input) | Recommends |
| **Design UX for AI** | ✅ | - |
| **Build eval framework** | ✅ Designs | ✅ Implements |
| **Model fine-tuning** | Defines requirements | ✅ |
| **Optimize inference** | Sets SLAs | ✅ |
| **Train models** | - | ✅ |
| **MLOps infrastructure** | Defines needs | ✅ |

**Key Insight**: PMs own product decisions (what, why, when). Engineers own implementation (how).

---

## The AI Metrics Framework

Every AI feature needs these 5 metric categories:

### 1. Model Performance
```
Classification: Accuracy, Precision, Recall, F1
Generation: BLEU, ROUGE, Human preference score
Relevance: MRR, NDCG (for search/recommendations)

PM Role: Define acceptable thresholds
Example: "95% accuracy on eval set, < 1% hallucination rate"
```

### 2. User Experience
```
Latency: p50, p95, p99 response time
Streaming: Time to first token
Error rate: 4xx, 5xx, timeouts

PM Role: Set SLAs based on UX research
Example: "p95 latency < 2 seconds, 99.9% uptime"
```

### 3. Business Impact
```
Adoption: % users who try the feature
Engagement: Sessions per user, retention
Conversion: Does AI improve funnel metrics?
Satisfaction: CSAT, NPS for AI features

PM Role: Define primary success metric
Example: "AI search increases task completion by 15%"
```

### 4. Safety & Quality
```
Hallucination rate: % of false/misleading outputs
Toxicity score: Harmful content detection
PII leakage: Privacy violations
Bias metrics: Fairness across demographics

PM Role: Set non-negotiable guardrails
Example: "Zero tolerance for PII in outputs"
```

### 5. Operational
```
Cost: $/request, $/user, $/month
Token usage: Input/output token distribution
Model drift: Performance degradation over time
Cache hit rate: Prompt/response caching efficiency

PM Role: Own P&L, cost targets
Example: "AI feature must be < $0.10/user/month"
```

---

## Prompt Engineering Cheat Sheet

### Basic Structure
```
[System Prompt]
You are an expert customer support agent...

[Instructions]
1. Read the customer message
2. Check the knowledge base
3. Draft a helpful response

[Examples] (few-shot)
Customer: "How do I reset my password?"
Agent: "I can help you reset your password..."

[Input]
Customer: {{user_message}}

[Output Format]
Response: ...
Confidence: [high/medium/low]
```

### Advanced Techniques

**Chain of Thought (CoT)**
```
Prompt: "Let's think step by step before answering..."
Use for: Math, reasoning, complex analysis
Tradeoff: Slower, more tokens, but more accurate
```

**Few-Shot Learning**
```
Provide 3-5 examples in the prompt
Use for: Formatting, tone, edge cases
Tradeoff: Uses context window, but big quality boost
```

**Self-Consistency**
```
Generate 5 answers, pick most common
Use for: High-stakes decisions, ambiguous questions
Tradeoff: 5x cost, but higher reliability
```

**Prompt Chaining**
```
Break complex task into steps:
Step 1: Extract key info → LLM call 1
Step 2: Research context → LLM call 2
Step 3: Generate answer → LLM call 3
Use for: Complex workflows, agentic systems
Tradeoff: More latency, but better quality
```

### Production Checklist
- [ ] Versioned in Git or prompt management system
- [ ] A/B tested against baseline
- [ ] Monitored for performance over time
- [ ] Has fallback prompt for failures
- [ ] Token budget calculated
- [ ] Guardrails for harmful outputs
- [ ] Examples cover edge cases

---

## Agent Architecture Patterns

### Pattern 1: Single Agent + Tools
```
[LLM] → [Tool Call] → [Result] → [LLM] → [Answer]

Example: Research agent
- Tool: Web search
- Flow: Question → Search → Read → Synthesize → Answer

Best for: Simple workflows, low latency needs
Framework: LangChain, OpenAI Agents SDK
```

### Pattern 2: Sequential Agent Chain
```
[Agent 1] → [Output] → [Agent 2] → [Output] → [Agent 3]

Example: Content pipeline
- Agent 1: Research topic
- Agent 2: Write draft
- Agent 3: Edit and format

Best for: Multi-step processes, specialization
Framework: LangChain, CrewAI
```

### Pattern 3: Parallel Agent Team
```
        [Agent 1]
[Input] [Agent 2] → [Synthesis] → [Output]
        [Agent 3]

Example: Code review
- Agent 1: Check style
- Agent 2: Check security
- Agent 3: Check performance
- Synthesis: Combine feedback

Best for: Parallel tasks, speed
Framework: CrewAI, AutoGen
```

### Pattern 4: Stateful Agent Loop
```
[LLM] → [Plan] → [Act] → [Observe] → [Reflect] → [Loop or Exit]

Example: Coding agent (Claude Code, Devin)
- Plan: What to build
- Act: Write code
- Observe: Run tests
- Reflect: Tests pass? If no, loop

Best for: Complex, iterative tasks
Framework: LangGraph, AutoGen
```

### Pattern 5: Human-in-the-Loop
```
[Agent] → [Draft] → [Human Review] → [Approve/Reject] → [Execute]

Example: Customer support
- Agent: Draft response
- Human: Review, edit
- System: Send to customer

Best for: High-stakes decisions, building trust
Framework: Any (add approval step)
```

---

## Cost Optimization Playbook

### Model Selection Strategy

| Use Case | Model Tier | Example | Cost |
|----------|-----------|---------|------|
| Simple tasks | Small/Fast | GPT-3.5, Claude Haiku | ~$0.001/req |
| Balanced | Medium | GPT-4o, Claude Sonnet | ~$0.01/req |
| Complex reasoning | Large | GPT-4, Claude Opus | ~$0.05/req |
| Specialized | Fine-tuned | Your custom model | Varies |

**PM Rule**: Use the cheapest model that meets quality bar.

### Prompt Optimization

1. **Shorten prompts**: Every token costs money
   - Bad: 500-word system prompt
   - Good: 100-word system prompt with same info

2. **Cache system prompts**: Anthropic offers prompt caching
   - Save 90% on repeated system prompts
   - Huge win for high-volume features

3. **Batch requests**: Group similar requests
   - Lower latency overhead
   - Better rate limit utilization

4. **Stop sequences**: Prevent over-generation
   - Set max tokens to prevent rambling
   - Use stop sequences to end early

### Architectural Optimizations

1. **Tier requests by complexity**
   ```
   Simple question → GPT-3.5 ($)
   If unsure → GPT-4 ($$)
   If still unsure → Human ($$$)
   ```

2. **Response caching**
   ```
   Check cache for exact match → Return instantly
   Check semantic cache → Return similar answer
   Else → Call LLM
   ```

3. **Streaming for UX**
   ```
   Start showing response immediately
   User perceives faster, same actual cost
   ```

---

## The 3-2-1 Rule for AI PM Success

### 3 Questions Before Building Any AI Feature

1. **Can we solve this without AI?**
   - If yes, do that (simpler, cheaper, more reliable)
   - AI is not a strategy, it's a tool

2. **What's the failure mode?**
   - Hallucination → User gets wrong info → Harm?
   - Identify risks before building

3. **How do we measure success?**
   - Define metrics upfront
   - Build eval suite before feature

### 2 Non-Negotiables for Production

1. **Automated eval suite**
   - 50+ test cases minimum
   - Re-run on every change
   - No evals = don't ship

2. **Cost model**
   - $/request, $/user, $/month
   - Set budgets and alerts
   - Cost overruns kill products

### 1 Metric That Matters Most

**User value delivered** (not AI sophistication)

- Don't optimize for cool tech
- Optimize for solving user problems
- Simple AI that works > Complex AI that impresses

---

## Common Failure Modes & Fixes

| Failure Mode | Symptoms | Fix |
|--------------|----------|-----|
| **Hallucination** | Model invents false info | Add grounding (RAG), require citations, human review |
| **Prompt injection** | User hijacks system prompt | Input sanitization, output filtering, red teaming |
| **Cost explosion** | Bill 10x higher than expected | Token budgets, cheaper models, caching, circuit breakers |
| **Latency spikes** | Slow responses, timeouts | Streaming, caching, async processing, smaller models |
| **Model drift** | Performance degrades over time | Monitor metrics, re-run evals, refresh training data |
| **Data poisoning** | Bad training data → bad outputs | Data quality checks, human review, versioning |
| **Over-automation** | AI makes high-stakes mistakes | Human-in-the-loop, confidence thresholds, escalation |

---

## The AI PM Reading List

### Must-Read (Week 1)
- Anthropic's "How Claude Works" (30 min)
- OpenAI's GPT-4 System Card (60 min)
- Lenny's AI Prototyping Guide (90 min)

### Month 1 (Foundations)
- "Building LLM Applications for Production" (Chip Huyen)
- "AI Engineering" (Swyx, Alessio)
- "The AI PM Playbook" (Aakash Gupta)

### Month 2 (Evaluation & Safety)
- Google's PAIR Guidebook
- Anthropic's Constitutional AI (summary)
- "Evaluating LLMs" (Comet ML blog)

### Month 3 (Agentic AI)
- LangChain documentation (agents section)
- LangGraph tutorials
- "Multi-Agent Systems" (Microsoft AutoGen blog)

### Ongoing
- Lenny's Newsletter (AI PM content)
- First Round Review (AI case studies)
- Anthropic, OpenAI, Google AI blogs

---

## When to Use This Roadmap

### You're Ready If...
- ✅ You're a PM with cloud/infrastructure/data platform experience
- ✅ You want to transition to AI product work
- ✅ You can commit 10-15 hours/week for 12 weeks
- ✅ You want practical skills, not academic theory
- ✅ You're comfortable learning by building

### This Roadmap Is NOT For...
- ❌ Learning ML engineering or data science
- ❌ Getting a PhD in AI
- ❌ Academic research
- ❌ Becoming an AI expert in 12 weeks (impossible)
- ❌ People with zero PM experience (learn PM fundamentals first)

### After Completing This Roadmap, You Can...
- ✅ Prototype AI features in hours using no-code tools
- ✅ Write production-quality prompts and manage them
- ✅ Build evaluation frameworks for AI features
- ✅ Design multi-agent systems with modern frameworks
- ✅ Make build vs buy decisions for AI capabilities
- ✅ Write PRDs for AI features with technical depth
- ✅ Collaborate effectively with ML engineers
- ✅ Ship AI products at Netflix/Google/Anthropic-level companies

---

## FAQ

**Q: I don't have a technical background. Can I still do this?**

A: If you have cloud/data platform experience (the target audience), yes. If you have zero technical background, learn PM fundamentals first, then come back to this.

**Q: Do I need to learn Python?**

A: No. This roadmap focuses on PM skills, not coding. You'll use no-code tools (Bolt, v0) and managed platforms (PromptLayer, Langfuse). Python is nice-to-have, not required.

**Q: What if I fall behind schedule?**

A: Adjust the timeline. The roadmap assumes 12 weeks, but you can stretch to 16-20 weeks if needed. Focus on completing the 3 milestone projects—that's where the learning happens.

**Q: Should I do all 3 projects, or can I skip?**

A: Do all 3. They're designed to force application of learning. Week 4 = prototyping, Week 8 = evaluation, Week 12 = agentic systems. Each builds on the last.

**Q: Which tools should I prioritize if I'm short on time?**

**Must-have**:
- Prototyping: Bolt.new or v0.dev (pick one)
- Evaluation: Langfuse or PromptLayer (pick one)
- Agentic: LangChain (start here)

**Nice-to-have**:
- Cursor, Replit, CrewAI, AutoGen (explore if you have time)

**Q: Is MCP really important, or just hype?**

A: MCP is early (launched Nov 2024) but rapidly gaining adoption (Google, OpenAI, Anthropic). It's not required for Week 1-8, but understanding it by Week 9-10 is valuable for 2025-2026 roadmaps.

**Q: How do I get an AI PM role after completing this?**

1. Build a portfolio (your 3 projects)
2. Write about your learnings (LinkedIn, blog)
3. Apply to AI-adjacent roles at your current company
4. Network with AI PMs (Lenny's community, Product School)
5. Target companies shipping AI (use the case studies section)

**Q: What's the ROI of this roadmap?**

- **Time**: 140-150 hours
- **Cost**: ~$100-200 (tool subscriptions for 3 months)
- **Outcome**: Ability to ship AI features, qualify for AI PM roles

Market data: AI PM salaries are 20-40% higher than traditional PM roles. Demand is growing 3x faster than supply (LinkedIn, 2025).

---

**Last Updated**: November 2025

**Feedback**: This is a living document. AI tooling evolves rapidly. If tools become outdated or new frameworks emerge, the principles remain the same: prototype fast, evaluate rigorously, ship responsibly.
