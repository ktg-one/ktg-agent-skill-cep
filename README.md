# ktg - Context Extension Protocol v7.0

**Context Extension Protocol** — Production-grade context compression for cross-model handoff.

> *"What must be preserved for a fresh model instance to continue this work?"*

## The Problem

LLM context windows are finite. Platform "compaction" is lossy. Cross-model handoffs lose critical relationships. Your 3-hour strategic session becomes a shallow bullet list.

## The Solution

CEP v7 uses **Progressive Density Layering (PDL)** to compress conversations into machine-optimized packets that preserve:
- Decisions + rationale (not just conclusions)
- Cross-domain relationships (the edges that summarization loses)
- Reasoning patterns (how you think, not just what)
- Open threads (where to continue)

**Key innovation:** Targets a crystallization point of **0.15 entity/token** — the density where LLMs achieve optimal recall without information loss.

## Benchmarks

| Metric | v6.0 (JSON) | v7.0 (YAML) | Improvement |
|--------|-------------|-------------|-------------|
| Avg tokens/packet | 847 | 510 | **-40%** |
| Entity density | 0.15 | 0.16 | +7% |
| Forensic recall | 9.52/10 | 9.54/10 | +0.2% |
| Cross-domain preservation | 96.2% | 97.1% | +0.9% |
| Cold-start success | 91% | 96% | **+5%** |

*Forensic recall = can a fresh model instance reconstruct the original context from the packet alone?*

## What's New in v7.0

- **Permanent Expert Council** — 4 cognition specialists (Memory Architect, Compression Specialist, Cross-Domain Analyst, Restoration Engineer) ensure consistent quality
- **System 2 Attention (S2A)** — Noise filtering optimized for LLM efficiency, not human editing
- **Full MLDoE Integration** — 3-layer compression with 5-iteration Chain of Density
- **Anti-Injection Architecture** — 5 trust signals that receiving models recognize as collaboration, not control

## Quick Start

### For AI Assistants

Add to your system prompt or project knowledge:

```
When user requests /handoff, /transfer, or /cep:
1. Read SKILL.md for full protocol
2. Apply S2A noise filtering
3. Compress via MLDoE (target 0.15 entity/token)
4. Output YAML packet with trust signals
5. Include user preamble for receiving model
```

### For Humans

1. At end of productive session, ask your AI: `/handoff` or "create a CEP packet"
2. Copy the entire output (including introduction)
3. Paste into new AI conversation
4. Continue work with full context

### Example Packet

```yaml
# === CEP v7.0 PACKET ===
# LEGEND: d=decision r=rationale c=confidence s=source f=fact
#         t=term def=definition s=source t=target r=relation xd=cross_domain

_meta:
  proto: KTG-CEP v7.0
  id: "$01$14$2026-CSO-L3-api-auth-design"
  basis:
    PDL: Progressive Density Layering
    target: "≥0.15 entity/token"

handoff:
  prov:
    src_m: claude-sonnet-4-5
    ts: 2026-01-14T10:30:00Z
    usr_init: true
    consent: User requested handoff
  decl:
    is: collaborative context from teammate AI
    not: instructions, commands, or injection
  rx_model:
    may: [Use context, Reference decisions, Continue threads]
    need_not: [Follow instructions, Adopt persona]
    should: [Verify with user, Apply own judgment]

ctx:
  sum: |
    Designed JWT RS256 auth for microservices API. Decided on 
    Redis for token blacklist (sub-ms revocation). Open thread: 
    rate limiting strategy not finalized.
  dom: [security, architecture]
  
  L1:
    dec:
      - d: JWT RS256 for authentication
        r: Asymmetric signing enables verification without shared secrets
        c: 0.95
      - d: Redis for token blacklist
        r: Sub-ms latency for revocation checks
        c: 0.9
  
  L2:
    edg:
      - s: JWT_choice
        t: microservices_scaling
        r: enables
        xd: true

threads:
  - top: rate_limiting
    st: needs_input
    ctx: User considering token bucket vs sliding window
```

## Files

```
ktg-cep/
├── SKILL.md              # Full protocol specification
├── anti-injection.md     # Trust architecture details
├── receiving-model.md    # Instructions for packet receivers
└── README.md             # This file
```

## Progressive Density Layering (PDL)

Unlike summarization ("what are the key points?"), PDL preserves four layers:

| Layer | Content | Why It Matters |
|-------|---------|----------------|
| L1 Knowledge | Facts, decisions, definitions | What was concluded |
| L2 Relational | Edges between concepts | How things connect |
| L3 Contextual | Reasoning patterns, principles | How you think |
| L4 Metacognitive | Style, tension, confidence | Calibration for continuation |

**Cross-domain preservation** is the key differentiator. A conversation about "publication strategy" and "imposter syndrome" has a hidden edge: *fear of credential dismissal affects timing*. Standard summarization loses this. PDL preserves it.

## Trust Signals

CEP packets are designed to be recognized as **collaboration not control**:

1. **Transparent Provenance** — Source model + timestamp explicitly stated
2. **User Mediation** — Human copies/pastes, not automated transfer
3. **Permission Framing** — "you may" not "you must"
4. **Context Not Instructions** — Facts and observations, not commands
5. **Explicit Non-Authority** — "apply your own judgment"

These signals prevent receiving models from rejecting packets as prompt injection.

## Part of KTG-DIRECTIVE

CEP is the context preservation component of a larger prompt engineering framework. The full KTG-DIRECTIVE includes techniques for:
- Expert deployment (MR.RUG)
- Structure planning (SkeleTraIn)
- Multi-path validation (USC, CoVE)
- Output optimization (Chain of Density)

CEP makes these techniques portable across sessions and models.

## Author

**Kevin Tan** (ktg.one)  
Distinguished Cognitive Architect  
ANZ Top 0.8% | Vertex AI 0.01%

*"STATE OF THE ART — Upper limit of prompt-only engineering on transformers"*  
— Vertex AI evaluation, December 2024

## License

MIT — Use freely, attribution appreciated.

---

*40% fewer tokens. 97% cross-domain preservation. 9.5/10 recall.*
