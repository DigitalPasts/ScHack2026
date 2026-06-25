# Applying for AI Research Credits — DANES ScHack 2026
**Action document · June 2026**

> **Timing note:** The school runs July 6–10, 2026 — approximately four weeks away. Most programmes have a 4–8 week review cycle, meaning credits from Google Cloud and OpenAI will likely arrive *after* the school. Apply anyway: they will fund follow-up research, the 2027 edition, and participant projects. For the July school itself, plan to pay for API access directly (€150–400 total — see llm-access-options.md) and treat credits as a medium-term asset.
>
> **Exception:** Anthropic's AI for Science programme has a shorter review cycle and may come through in time. Prioritise that application.

---

## 1. Anthropic — AI for Science Programme
**Potential credit:** Up to $20,000 (USD) in API credits for a 6-month period  
**Likelihood of approval:** High — digital humanities applied to ancient languages is a strong fit  
**Timeline:** Apply now; Anthropic reviews on a rolling basis

### What it covers
Free access to Anthropic's full model suite (Claude Sonnet, Haiku, Opus) via API for scientific research projects.

### Eligibility
- Must be affiliated with a research institution or academic organisation
- Research must be focused on applying generative AI to scientific questions
- Individual applicants must be 18+
- Not available to residents of Belarus, China, Cuba, Iran, Myanmar, North Korea, Russia, Sudan, Syria, or sanctioned territories

### Application link
**https://www.anthropic.com/news/ai-for-science-program** → click the application form link on this page

### What to write in the application

**Project title (suggested):**
> "Applying Large Language Models to Ancient Language Processing and Material Culture Analysis: DANES ScHack 2026"

**Project description (adapt as needed):**
> DANES ScHack 2026 is the first DANES (Digital Ancient Near Eastern Studies) Summer School and Hackathon, hosted at the University of Turin (July 6–10, 2026). The school brings together 35 confirmed participants — PhD students, postdoctoral researchers, and faculty — from 15 countries, working across three tracks: (1) Ancient Language Processing using NLP and LLMs on cuneiform, Akkadian, Sumerian, Hittite, and Greek corpora; (2) Computer Vision for Material Culture, applying image classification, object detection, and HTR to archaeological artefacts and manuscripts; and (3) Network Analysis. Tracks 1 and 2 require direct LLM API access for hands-on teaching and hackathon sessions. Specific applications include: RAG-based querying of the ORACC/CDLI cuneiform corpora; few-shot and chain-of-thought prompting for lacuna reconstruction in fragmentary ancient texts; LLM-based annotation of iconographic datasets (Egyptian tomb scenes, Late Bronze Age artefacts); and multimodal analysis combining textual and visual ancient evidence. The event is organised under the DANES Network (opendanes.org) in partnership with the University of Turin, KU Leuven, UCLouvain, Charles University Prague, and other institutions.

**Research institution:** Open University of Israel (DHSS) / University of Turin (host)  
**Principal contact:** Shai Gordin, Associate Professor, DHSS, Open University of Israel

---

## 2. Anthropic — External Researcher Access Programme
**Potential credit:** $500–$5,000 (USD) in API credits  
**Focus:** Primarily AI safety research — less directly relevant, but worth a short application  
**Timeline:** Rolling

### Application link
**https://support.claude.com/en/articles/9125743-what-is-the-external-researcher-access-program**  
→ Follow the "apply here" link in the article

### Notes
This programme focuses on AI safety and alignment research. Frame the application around the *evaluation and responsible use* of LLMs on low-resource ancient languages — i.e., what are the failure modes, hallucinations, and reliability limits of LLMs when applied to cuneiform? This is a legitimate research question your Track 1 cohort will actually be investigating.

---

## 3. OpenAI — Researcher Access Programme
**Potential credit:** Up to $1,000 (USD) in API credits, valid 12 months  
**Timeline:** Applications reviewed quarterly (March / June / September / December). June cycle may apply; otherwise September — credits will arrive ~October 2026.

### Application link
**https://openai.com/form/researcher-access-program/**  
(also accessible via https://openai.smapply.org/prog/openai_researcher_access_program/)

### Eligibility
- Active affiliation with an academic institution or research organisation
- Nonprofits conducting research (not operational support) are also eligible
- Credits cannot be extended or renewed after 12 months

### What to write

**Project title (suggested):**
> "Low-Resource Ancient Language Processing with LLMs: Evaluation and Application at DANES ScHack 2026"

**Project description (adapt):**
> This project evaluates the performance and limitations of large language models applied to ancient Near Eastern languages — Akkadian, Sumerian, and Hittite — which are severely low-resource, morphologically complex, and written in non-standard scripts (cuneiform transliteration). The work includes: (1) systematic comparison of zero-shot, few-shot, and RAG-augmented prompting strategies on cuneiform corpora (ORACC, CDLI); (2) evaluation of LLM-based lacuna reconstruction for fragmentary tablet texts; (3) multimodal LLM analysis of archaeological iconographic datasets. The research is conducted in the context of DANES ScHack 2026, a summer school and hackathon at the University of Turin (July 2026) bringing together 35 researchers from 15 countries. Results will be documented and made publicly available through the DANES Network (opendanes.org).

**Institutional affiliation:** Open University of Israel  
**Applicant role:** Faculty / Principal Investigator

### Key restriction to note
$1,000 covers approximately 200–700 teaching sessions at GPT-4o pricing, depending on prompt length. It is a useful supplement but not sufficient on its own for a week-long school — combine with direct purchase for July.

---

## 4. Google Cloud — Research Credits Programme
**Potential credit:** Up to $5,000 (USD) for faculty/postdoctoral researchers  
**Timeline:** Applications accepted on an ongoing basis; decisions in **6–8 weeks** — likely too late for July, but arrives in August for subsequent use

### Application link
**https://edu.google.com/programs/credits/research/**

### Eligibility
- Faculty, PhD students, and postdoctoral researchers at accredited higher education institutions
- Must be in an approved country (Israel, Italy, Belgium, Czech Republic, UK, Germany, Switzerland, USA, Spain, France all qualify)
- Must create a Google Cloud billing account before applying

### What to prepare before applying
1. Create a Google Cloud billing account at console.cloud.google.com
2. Draft a brief research proposal (300–500 words) explaining how you will use the credits
3. Estimate expected costs using the Google Cloud Pricing Calculator (cloud.google.com/products/calculator)

### What to write

**Research proposal (adapt):**
> This proposal requests Google Cloud credits to support two research applications at the DANES Network's first Summer School and Hackathon (University of Turin, July 2026) and in follow-up research activities:
>
> (1) **Vertex AI / Gemini API access** for LLM-based ancient language processing, including prompt engineering experiments on Akkadian and Sumerian corpora, RAG implementation using the ORACC/CDLI datasets, and multimodal analysis of archaeological image collections.
>
> (2) **Cloud compute (GCP) for CV pipelines**: training and running object detection models (YOLO/DETR) on iconographic datasets of ancient Egyptian, Levantine, and Mesopotamian material culture; HTR model training for Demotic and Hieratic Egyptian scripts.
>
> The school involves 35 participants from 15 countries; results and workflows will be published openly through the DANES Network (opendanes.org).

**Estimated credit use:** $3,000–$5,000 over 6 months (split between Gemini API calls and Compute Engine for CV training)

### Important: billing account
You need a Google Cloud billing account set up before submitting — without it, the application form cannot be completed.

---

## 5. Microsoft Azure — Research Credits
**Potential credit:** Variable; smaller grants available via standard programme  
**Timeline:** 4–6 weeks; apply after Google Cloud and Anthropic

### Application link
**https://www.microsoft.com/en-us/azure-academic-research/**

### Notes
Azure credits are most useful for accessing Azure OpenAI Service (which provides GPT-4o through Microsoft's infrastructure) rather than for compute alone. If you plan to use GPT-4o via Azure rather than directly through OpenAI, this is worth doing. The application process is similar to Google Cloud — submit a research proposal with a cost estimate.

For ScHack purposes, this is lower priority than Anthropic and Google Cloud.

---

## Recommended Application Order and Timeline

| # | Programme | Apply by | Expected decision | Credit value |
|---|---|---|---|---|
| 1 | **Anthropic AI for Science** | Today | Rolling — possibly before July | Up to $20,000 |
| 2 | **OpenAI Researcher Access** | Today | June review cycle | $1,000 |
| 3 | **Anthropic External Researcher** | This week | Rolling | $500–$5,000 |
| 4 | **Google Cloud Research Credits** | This week | Late July–August | Up to $5,000 |
| 5 | **Microsoft Azure Research** | Within 2 weeks | August–September | Variable |

**Total potential credits if all approved:** $25,000–$32,000 in API and compute credits — enough to run multiple future editions of ScHack with no infrastructure cost.

---

## Information you will need for every application

Have the following text ready — copy and adapt for each form:

**Organisation name:** Open University of Israel (DHSS) / DANES Network  
**Website:** https://opendanes.org  
**Event name:** DANES ScHack 2026 — First DANES Summer School and Hackathon  
**Host institution:** University of Turin, Italy  
**Dates:** July 6–10, 2026  
**Participants:** 35 confirmed, from 15 countries, across 3 tracks  
**Your role:** Academic Coordinator and Track 1 lead instructor  
**Co-organisers:** Maurizio Viano and Elena Devecchi (University of Turin)  
**Primary use case:** LLM API access for teaching and hands-on research in ancient language processing and computer vision  

**One-line project description:**  
> Applying and evaluating large language models for the analysis of ancient Near Eastern languages and archaeological material culture, in the context of an international academic summer school.

---

## Sources

- [Anthropic AI for Science Programme](https://www.anthropic.com/news/ai-for-science-program)
- [Anthropic AI for Science — Programme Rules](https://www.anthropic.com/ai-for-science-program-rules)
- [Anthropic External Researcher Access Programme](https://support.claude.com/en/articles/9125743-what-is-the-external-researcher-access-program)
- [OpenAI Researcher Access Programme — Application Form](https://openai.com/form/researcher-access-program/)
- [OpenAI Researcher Access Programme — FAQ](https://help.openai.com/en/articles/10139500-researcher-access-program-faq)
- [OpenAI Researcher Access Programme — smapply portal](https://openai.smapply.org/prog/openai_researcher_access_program/)
- [Google Cloud Research Credits Programme](https://edu.google.com/programs/credits/research/)
- [Google Cloud Research Credits — Application Guidelines](https://support.google.com/google-cloud-higher-ed/answer/10724468?hl=en)
- [Microsoft Azure Academic Research](https://www.microsoft.com/en-us/azure-academic-research/)
