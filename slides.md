# Slide Deck: The Evolution of RAG
## CMPE-297 Short Story Presentation
### Nikita Memane | Fall 2026

---

## Slide 1: Title Slide
**The Evolution of RAG: From Simple Retrieval to Intelligent Generation**
- Nikita Memane
- CMPE-297 Special Topics in Data Mining
- San Jose State University, Fall 2026
- Survey: "Rethinking Knowledge Retrieval for Generation" (Sunil et al., Oct 2026)

---

## Slide 2: The Problem with LLMs
- Knowledge is frozen at training time
- Hallucination: confident but incorrect answers
- Cannot access real-time or domain-specific information
- Production deployment requires accuracy and verifiability
- **Solution: Retrieval-Augmented Generation (RAG)**

---

## Slide 3: What is RAG?
- Three core components:
  1. **Retrieve**: Fetch relevant documents from external knowledge base
  2. **Augment**: Combine retrieved context with the query
  3. **Generate**: LLM produces output grounded in both query + evidence
- Formally: P(y|x) = Σ P(y|x,d) · P(d|x) over retrieved docs D
- Key insight: Dynamic knowledge injection vs. static parametric memory

---

## Slide 4: RAG Pipeline Diagram
[Include Figure: Standard RAG pipeline]
- User Query → Embedding → Vector DB Search → Top-K Documents → LLM → Response
- Offline: Documents → Chunking → Embedding → Vector Store
- Online: Query → Retrieve → Augment → Generate

---

## Slide 5: Three Generations of RAG
| Generation | Description | Limitation |
|------------|-------------|------------|
| **Naive RAG** | Retrieve top-k, concatenate, generate | No filtering, no feedback |
| **Advanced RAG** | Pre/post-retrieval processing, re-ranking, self-reflection | Still fixed pipeline |
| **Modular RAG** | Interchangeable components, adaptive retrieval decisions | Current frontier (2026) |

---

## Slide 6: Four-Axis Taxonomy (Survey's Core Contribution)
The survey organizes all recent RAG work into four dimensions:
1. 🔧 **Compression & Efficiency** — Speed and cost optimization
2. 🛡️ **Defensive RAG** — Security, bias, privacy
3. 👤 **User-Centric RAG** — Personalization and interaction
4. 🧠 **Complex Reasoning** — Multi-step, multi-hop tasks

---

## Slide 7: Axis 1 — Compression & Efficiency
**Goal**: Balance retrieval quality against latency and cost
- **RETRO**: Integrates retrieval into transformer layers directly
- **xRAG**: Extreme context distillation into compact representations
- **RAPTOR**: Recursive tree-based hierarchical retrieval (multi-granularity)
- **Stochastic RAG**: Probabilistic sampling to reduce documents processed
- Objective: maximize information per token (log-efficiency score)

---

## Slide 8: Axis 2 — Defensive RAG
**Goal**: Make RAG systems trustworthy and robust
- **PoisonedRAG**: Adversarial attacks achieve 97-99% success rate
- **SELF-RAG**: Self-reflective retrieve → generate → critique loop
- **Bias frameworks**: BiasBench, MuslimBias detect amplified demographic bias
- **Controlled noise injection**: Adding distractors improves calibration
- Risk score: S = (1−Toxicity) + Privacy + Bias
- Shift: Relevance → Relevance × Trustworthiness

---

## Slide 9: Axis 3 — Interactive, User-Centric RAG
**Goal**: Move from "retrieval-as-lookup" to "retrieval-as-dialogue"
- **ISEEQ**: Generates clarifying questions for ambiguous queries
- **PersonaRAG**: User-profile-conditioned retrieval (94.73% accuracy on TriviaQA)
- **Active RAG**: Dynamically decides: retrieve, clarify, or use parametric knowledge
- **RA-DIT**: Dual instruction tuning with user interaction signals
- Scoring: Semantic relevance + Historical alignment + Feedback compatibility

---

## Slide 10: Axis 4 — Complex Reasoning
**Goal**: RAG systems that can reason, not just retrieve
- **PlanRAG**: Decomposes complex queries into sub-plans with per-step retrieval
- **Chain-of-Thought RAG**: Iterative retrieval as reasoning progresses
- **G-Retriever / GRAG**: Graph-structured knowledge base retrieval
- **MathPrompter**: RAG + mathematical verification
- **FRAMES benchmark**: Multi-hop reasoning accuracy 40.8%–72.9%

---

## Slide 11: Domain Applications & Results
| Domain | System | Key Result |
|--------|--------|------------|
| QA | FoRAG | Factuality 0.82–0.99 |
| Code | CodeT5+ | pass@1 35.0% |
| Conversational | PersonaRAG | Top-3 accuracy 94.73% |
| Healthcare | GPT-4.0-RAG | 91.4% accuracy, 1.2% hallucination |
| Legal | CaseGPT | NDCG@10 0.91–0.93 |
| Education | Chipper | 84.40% accuracy |
| Robotics | TidyBot | 91.2% on unseen objects |

---

## Slide 12: RAG Evaluation Landscape
**Retrieval Metrics**: MRR, MAP, NDCG@10, Precision@10
**Generation Metrics**: Exact Match, F1, BLEU, Faithfulness
**End-to-End Frameworks**:
- **RAGAS**: Reference-free (no ground truth needed)
- **RAGBench**: Multi-domain, explainable
- **BERGEN**: Modular evaluation library
- **FlashRAG / RAGLAB**: Reproducible evaluation toolkits
**Gap**: Most benchmarks are English-only, single-hop QA

---

## Slide 13: Open Challenges
1. **Retrieval Bottlenecks**: Static indexes, chunk-size trade-offs, latency
2. **Hallucination Propagation**: Noisy retrieval amplified by generator
3. **Domain Adaptation**: General embeddings fail on specialized vocabularies
4. **Scalability**: Billions of documents require ANN, distributed retrieval, caching
5. **Explainability**: Users need provenance and attribution

---

## Slide 14: Future Directions
1. **RL for RAG**: Joint retrieval-generation optimization as sequential decisions
2. **Neuro-Symbolic**: Ontology-guided retrieval + symbolic verification
3. **Multi-Modal RAG**: Unified embeddings for text, images, tables, video, audio
4. **Better Benchmarks**: Attribution quality, multilingual, multi-hop, user satisfaction

---

## Slide 15: My Perspective — Building Production RAG
From my CMPE-295 Self-Healing RAG Platform on Kubernetes:
- **Retrieval quality is the ceiling** — better chunking beats a bigger LLM
- **Self-healing is essential** — embeddings drift, documents change silently
- **Autonomous detection + correction loop** — no labeled data needed
- **Dual-gate promotion** — quality AND performance gates before deployment
- **Reference-free evaluation** (RAGAS) — ground truth does not scale in dynamic KBs
- Bridges the gap between academic RAG and production systems

---

## Slide 16: Key Takeaways
1. RAG has evolved from simple retrieve-and-generate to a modular, adaptive paradigm
2. Four research axes: efficiency, security, interactivity, reasoning
3. Production RAG needs MLOps: monitoring, drift detection, self-healing
4. Evaluation is the hardest unsolved problem
5. The future is multi-modal, reasoning-capable, and user-aware RAG

---

## Slide 17: References
- Sunil et al. (2026). "Rethinking Knowledge Retrieval for Generation." arXiv:2610.01936
- Lewis et al. (2020). "Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks." NeurIPS.
- Asai et al. (2023). "Self-RAG: Learning to Retrieve, Generate, and Critique."
- Es et al. (2024). "RAGAS: Automated Evaluation of RAG."
- Sarthi et al. (2024). "RAPTOR: Recursive Abstractive Processing for Tree-Organized Retrieval."

---

## Slide 18: Thank You
**Nikita Memane**
CMPE-297 | Fall 2026 | San Jose State University
- GitHub: [repo link]
- Medium: [article link]
- YouTube: [video link]
