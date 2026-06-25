# LLM Access for DANES ScHack 2026 — Tracks 1 & 2
**Planning document · June 2026**

---

## Context

Tracks 1 (Ancient Language Processing) and 2 (Computer Vision for Material Culture) both require participant access to large language models and vision-capable AI systems during morning sessions and hackathons. The key requirements are:

- **Track 1**: API-level access to LLMs for prompting exercises (zero-shot, few-shot, RAG, chain-of-thought); some participants will also need GPU compute for fine-tuning or treebank pipelines.
- **Track 2**: Access to vision-capable (multimodal) LLMs for image annotation and classification; GPU compute for running YOLO/DETR and HTR pipelines; photogrammetry tools are largely offline and not an issue.

---

## Option 1 — Shared API Key with a Proxy (Recommended primary solution)

**How it works:** The organisers purchase API access (OpenAI and/or Anthropic), then run a lightweight proxy server (e.g. **LiteLLM**, open-source) that gives each student a personal token with a per-user rate limit. Students point their Python scripts and notebooks at the proxy endpoint — they never see the underlying API key.

**Best models for this setup:**
| Model | Use case | Approximate cost |
|---|---|---|
| GPT-4o | Prompting, RAG, multimodal (Track 1 + 2) | ~€4 per million input tokens |
| GPT-4o-mini | High-volume exercises, beginner sessions | ~€0.12 per million input tokens |
| Claude 3.5 Sonnet | Long-context ancient text analysis (200k window) | ~€3 per million input tokens |
| Claude Haiku 3.5 | Fast, cheap responses for iteration | ~€0.07 per million input tokens |

**Estimated cost for one week (25 students, Tracks 1+2):** €150–400 depending on session intensity. A hard spending cap on the OpenAI/Anthropic dashboard eliminates cost overrun risk.

**Setup time:** 1–2 hours. LiteLLM can be run on any small cloud VM or even on a laptop.

**Pros:** Clean, professional, works with any Python library (openai, anthropic, LangChain), no student accounts required, rate limits prevent runaway costs.

**Cons:** Requires someone to stand up the proxy before the school; needs stable internet at the venue.

---

## Option 2 — Google AI Studio + Gemini API (Free tier, easiest to start)

**How it works:** Each student creates a free Google account (most already have one) and generates their own Gemini API key at [aistudio.google.com](https://aistudio.google.com). No credit card required for the free tier.

**Key advantage — context window:** Gemini 1.5 Pro offers a **1 million token context window**, which is exceptional for Track 1 participants who want to feed an entire cuneiform corpus into a single prompt.

**Free tier limits (as of mid-2025):** 15 requests/minute, 1,500 requests/day per key — sufficient for workshop use if sessions are paced.

**Multimodal:** Gemini 1.5 Pro and Gemini 1.5 Flash both support image input, which covers Track 2 multimodal exercises.

**Pros:** Zero cost, zero setup for organisers, students keep access after the school.

**Cons:** Quality slightly below GPT-4o for nuanced language tasks; rate limits can be frustrating during simultaneous class exercises; free tier may change.

---

## Option 3 — Google Colab (GPU compute for both tracks)

**How it works:** Students run Python notebooks in a browser, with free access to a T4 GPU. No local installation required — critical for a diverse international cohort with varied hardware.

**Why this matters:**
- **Track 1**: Running small HuggingFace models (e.g. camelBERT, ancient-Greek BERT, UD-pipe), fine-tuning demos, YOLO for sign detection (Liubov's use case).
- **Track 2**: Running YOLO/DETR object detection, Kraken/Transkribus-style HTR pipelines, GigaMesh is offline but CV pipelines need GPU.

**Colab tiers:**
| Tier | Cost | GPU | Best for |
|---|---|---|---|
| Free | €0 | T4 (limited hours/day) | Beginner exercises, inference |
| Colab Pro | ~€10/month | T4/L4, more hours | Most Track 1 + 2 exercises |
| Colab Pro+ | ~€50/month | A100, background execution | Heavy fine-tuning, Track 2 pipelines |

**Recommendation:** Ask participants to have a Google account. For the most compute-intensive sessions (fine-tuning demos, YOLO training), the teacher runs the computation live and students observe + edit notebooks collaboratively rather than each running their own job.

---

## Option 4 — Local Server with Ollama (Offline fallback, privacy-safe)

**How it works:** Install **Ollama** on a university machine or a rented server with a GPU (e.g. a single NVIDIA A100/H100 instance on AWS/Azure, ~€3–5/hour). Students connect to it over the local Wi-Fi network — no internet required after setup.

**Recommended models:**
| Model | Size | Quality notes |
|---|---|---|
| Llama 3.1 70B (Q4) | ~40 GB VRAM | Best open-source general capability; good for prompting exercises |
| Mistral 7B / Mixtral 8x7B | 5–26 GB VRAM | Fast; sufficient for beginner sessions |
| Phi-3 Medium | 8 GB VRAM | Very capable for its size; runs on consumer hardware |
| LLaVA / BakLLaVA | 7–13 GB VRAM | Open-source multimodal, useful for Track 2 demos |

**Why this is valuable:** Some participants may be working with unpublished datasets or sensitive archival material. A local server ensures nothing leaves the room. Also useful as a fallback if the venue internet is unreliable (a real risk at Italian universities in summer).

**Setup time:** 2–3 hours, best done 1–2 days before the school opens.

**Cons:** Quality gap vs. GPT-4o is noticeable for complex reasoning; requires someone to manage the server; hardware cost if renting a GPU instance.

---

## Option 5 — Hugging Face Inference API + Spaces (Supplementary)

**How it works:** HuggingFace provides a serverless inference API for most public models and a "ZeroGPU" Space tier that gives free GPU access for interactive demos. Several ancient-language models are hosted here (e.g., models trained on Akkadian, Greek, Latin).

**Best uses:**
- Pre-built **ancient-language models**: search the Hub for Akkadian/Sumerian/Greek NLP models that students can run immediately without training.
- **ZeroGPU Spaces**: Teachers can build a demo Space before the school (a simple web UI wrapping a model) and students interact with it through the browser — no Python setup required.
- **Supplementary API calls** for open-source models when OpenAI/Anthropic credits are running low.

**Cons:** Less reliable latency than a dedicated proxy; some models are very large and slow on the free tier; requires a HuggingFace account per user.

---

## Option 6 — Apply for Academic / Research Credits

Several providers offer grants or credits for educational events. Lead time is typically 4–8 weeks.

| Provider | Programme | What you get |
|---|---|---|
| OpenAI | Researcher Access Program | API credits for academic research |
| Anthropic | Claude for Education (via contact) | API credits; contact education@anthropic.com |
| Google Cloud | Google for Education / TPU Research Cloud | Cloud credits; apply at cloud.google.com/edu |
| Microsoft Azure | Azure for Research | Azure credits; includes Azure OpenAI access |
| AWS | AWS Educate / Research Credits | AWS credits usable for SageMaker/Bedrock |

**Recommendation:** Apply to 2–3 of these immediately. Even partial credits (€200–500 worth) meaningfully reduce cost. Mention that this is the first DANES summer school — a funded academic event with international participants is a good application.

---

## Recommended Setup for ScHack 2026

Given the timeline (July 2026) and the mixed-experience cohort:

### Primary stack
1. **LiteLLM proxy** pointing to **OpenAI GPT-4o + GPT-4o-mini** — covers both tracks, most reliable, easiest for participants to use.
2. **Google Colab** for all notebook-based sessions — removes local installation friction entirely.
3. **Gemini API (free tier)** as a personal backup each student can keep using after the school.

### Track-specific additions
- **Track 1**: Add Claude Sonnet access (via the same LiteLLM proxy) for long-context ancient corpus work. Prepopulate Colab notebooks with a pre-configured `anthropic` client.
- **Track 2**: Budget for Colab Pro for the 3–5 most compute-intensive sessions (YOLO training, HTR pipeline). Teachers run the heavy jobs live; students interact with outputs.

### Fallback
- **Ollama local server** on a rented A100 instance (or the University IT server if available), loaded with Llama 3.1 70B and LLaVA. Activate only if venue internet proves unreliable or a participant has data privacy concerns.

---

## Practical Checklist (pre-school)

- [ ] Set up OpenAI organisation account with €300 spending cap; enable GPT-4o and GPT-4o-mini.
- [ ] Set up Anthropic API account with €150 spending cap; enable Claude Sonnet and Haiku.
- [ ] Deploy LiteLLM proxy on a small VM (or a spare laptop); generate one token per participant.
- [ ] Create a shared Google Colab folder with pre-configured notebooks; verify GPU availability.
- [ ] Apply for Google Cloud / Anthropic educational credits (do this now if not already done).
- [ ] Confirm with University of Turin IT whether a GPU-equipped server is available on-site.
- [ ] Test the full stack 48 hours before the school opens with at least one teacher.
- [ ] Prepare a one-page "Getting Started" handout: how to install the `openai`/`anthropic` Python package, how to get their LiteLLM token, how to open the shared Colab notebooks.
