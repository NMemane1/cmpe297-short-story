# CMPE-297 Short Story: The Evolution of RAG

**Author:** Nikita Memane  
**Course:** CMPE-297 Special Topics in Data Mining, Fall 2026  
**University:** San Jose State University  

## Overview

This repository contains all deliverables for the CMPE-297 Short Story assignment. The short story is based on a comprehensive survey of **Retrieval-Augmented Generation (RAG)** architectures and applications, summarizing the latest research trends, taxonomies, and evaluation methods in the RAG ecosystem.

## Survey Paper

**"Rethinking Knowledge Retrieval for Generation: A Survey on RAG Architectures and Applications"**  
*Meghana Sunil, Shravya V, Shravan Venkatraman, Joe Dhanith P R*  
VIT Chennai | Published October 2026  
[arXiv:2610.01936](https://arxiv.org/abs/2610.01936)

### What the Survey Covers
- Formalization of RAG as three components: retrieval, augmentation, and generation
- Evolution from Naive RAG → Advanced RAG → Modular RAG
- Four-axis taxonomy: Efficiency, Defensive RAG, User-Centric Interaction, Complex Reasoning
- Domain applications across QA, code generation, healthcare, legal, and education
- Evaluation frameworks (RAGAS, RAGBench, BERGEN) and open challenges
- Future directions: RL for RAG, neuro-symbolic integration, multi-modal retrieval

## Deliverables

| Deliverable | Link |
|-------------|------|
| **Medium Article** | [The Evolution of RAG: From Simple Retrieval to Intelligent Generation](TODO) |
| **SlideShare Deck** | [Slide Deck](TODO) |
| **YouTube Presentation** | [15-min Video Walkthrough](TODO) |
| **Article Draft (Markdown)** | [article.md](article.md) |
| **Slide Deck (Markdown)** | [slides.md](slides.md) |

## Key Topics Covered

### RAG Taxonomy
- **Naive RAG**: Simple retrieve → concatenate → generate
- **Advanced RAG**: Pre/post-retrieval processing, re-ranking, self-reflection (SELF-RAG)
- **Modular RAG**: Interchangeable components, adaptive retrieval decisions

### Four Research Axes
1. **Compression & Efficiency**: RETRO, xRAG, RAPTOR, Stochastic RAG
2. **Defensive RAG**: PoisonedRAG attacks (97-99% ASR), SELF-RAG, bias detection
3. **User-Centric RAG**: PersonaRAG (94.73% accuracy), ISEEQ, Active RAG
4. **Complex Reasoning**: PlanRAG, Chain-of-Thought RAG, G-Retriever, FRAMES

### Key Results from the Survey
| System | Domain | Result |
|--------|--------|--------|
| FoRAG | QA | Factuality 0.82-0.99 |
| CodeT5+ | Code Generation | pass@1 35.0% |
| PersonaRAG | Conversational | Top-3 accuracy 94.73% |
| GPT-4.0-RAG | Healthcare | 91.4% accuracy, 1.2% hallucination |
| CaseGPT | Legal | NDCG@10 0.91-0.93 |

### My Perspective
As the developer of a **Self-Healing RAG Platform on Kubernetes** (CMPE-295 Master's Project), I bring hands-on production experience to this survey. Key insights:
- Retrieval quality is the ceiling for generation quality
- Self-healing and drift detection are essential for production RAG
- Reference-free evaluation (RAGAS) scales where ground truth cannot
- Dual-gate promotion patterns ensure safe pipeline updates

## Repository Structure

```
cmpe297-short-story/
├── README.md              # This file
├── article.md             # Medium article draft (Markdown)
├── slides.md              # Slide deck content (Markdown)
└── slides.pptx            # PowerPoint presentation (for SlideShare)
```

## How to Use

1. **Read the article**: Start with [article.md](article.md) for the full Medium article draft
2. **Review slides**: See [slides.md](slides.md) for the presentation content
3. **Watch the video**: YouTube link above for the full 15-minute walkthrough

## References

1. Sunil, M., Shravya, V., Venkatraman, S., & Dhanith P R, J. (2026). *Rethinking Knowledge Retrieval for Generation: A Survey on RAG Architectures and Applications.* arXiv:2610.01936.
2. Lewis, P., et al. (2020). *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks.* NeurIPS 2020.
3. Asai, A., et al. (2023). *Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection.*
4. Es, S., et al. (2024). *RAGAS: Automated Evaluation of Retrieval Augmented Generation.*
5. Sarthi, P., et al. (2024). *RAPTOR: Recursive Abstractive Processing for Tree-Organized Retrieval.*

---

*San Jose State University | Department of Computer Engineering | Fall 2026*
