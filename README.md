# 🧬 NasTech Agent Self-Evolution

**Evolutionary self-improvement for [NasTech Agent](https://github.com/nastech-ai/NasTech-Agent).**

NasTech Agent Self-Evolution uses DSPy + GEPA (Genetic-Pareto Prompt Evolution) to automatically evolve and optimize NasTech Agent's skills, tool descriptions, system prompts, and code — producing measurably better versions through reflective evolutionary search.

**No GPU training required.** Everything operates via API calls — optimizing the *text* of prompts, instructions, and few-shot examples, not model weights.

## Quick Start

```bash
git clone https://github.com/nastech-ai/nastech-agent-self-evolution.git
cd nastech-agent-self-evolution
pip install -e ".[dev]"

# Point at your nastech-agent repo
export NASTECH_AGENT_REPO=~/.nastech/nastech-agent

# Evolve a skill
python -m evolution.skills.evolve_skill --skill github-code-review --iterations 10
```

## What It Optimizes

| Tier | Target | Engine | Risk |
|------|--------|--------|------|
| 1 | Skill files (SKILL.md) | DSPy + GEPA | Low |
| 2 | Tool descriptions | DSPy + GEPA | Low |
| 3 | System prompt sections | DSPy + GEPA | Medium |
| 4 | Code implementation | Darwinian Evolver | High |

## How It Works

```
Real Usage Data (SessionDB)
    │
    ▼
Evaluation Dataset Builder
    │
    ▼
DSPy Module (wraps skill/prompt/tool)
    │
    ▼
GEPA Optimizer ◄── Execution Traces
    │
    ▼
Candidate Variants ──► batch_runner (parallel evaluation)
    │
    ▼
Best Valid Variant ──► PR with metrics
```

## License

MIT License — Copyright © 2026 NasTech
