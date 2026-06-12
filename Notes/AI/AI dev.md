# 🤖 AI Engineer / LLM Engineer / AI Agent Developer / Generative AI Developer
# Ultimate Interview Questions & Answers (200+)

> **Covers:** AI Engineering · LLM Engineering · AI Agent Development · Generative AI · RAG · Fine-Tuning · Prompt Engineering · Vector Databases · Multi-Agent Systems · MLOps · System Design · Situational & Behavioral Questions

---

## 📋 Table of Contents

1. [Fundamentals of LLMs & AI](#1-fundamentals-of-llms--ai)
2. [Transformer Architecture & Attention](#2-transformer-architecture--attention)
3. [Tokenization & Embeddings](#3-tokenization--embeddings)
4. [Prompt Engineering](#4-prompt-engineering)
5. [Retrieval-Augmented Generation (RAG)](#5-retrieval-augmented-generation-rag)
6. [Vector Databases & Similarity Search](#6-vector-databases--similarity-search)
7. [Fine-Tuning & RLHF](#7-fine-tuning--rlhf)
8. [AI Agents & Agentic Systems](#8-ai-agents--agentic-systems)
9. [Multi-Agent Systems](#9-multi-agent-systems)
10. [Frameworks (LangChain, LangGraph, LlamaIndex, CrewAI)](#10-frameworks-langchain-langgraph-llamaindex-crewai)
11. [Generative AI (Images, Audio, Multimodal)](#11-generative-ai-images-audio-multimodal)
12. [LLM Evaluation & Metrics](#12-llm-evaluation--metrics)
13. [AI Safety, Guardrails & Ethics](#13-ai-safety-guardrails--ethics)
14. [MLOps & Production Deployment](#14-mlops--production-deployment)
15. [System Design for AI](#15-system-design-for-ai)
16. [Situational & Scenario-Based Questions](#16-situational--scenario-based-questions)
17. [Behavioral & HR Questions](#17-behavioral--hr-questions)
18. [Advanced & Research-Level Questions](#18-advanced--research-level-questions)

---

## 1. Fundamentals of LLMs & AI

---

### Q1. What is a Large Language Model (LLM) and how does it work?

**Answer:**
A Large Language Model is a deep learning model trained on massive text datasets to understand and generate human-like text. It is built on the Transformer architecture and works by:

1. **Tokenization** — Converting input text into tokens (sub-word units)
2. **Embedding** — Mapping tokens to high-dimensional vectors
3. **Attention Mechanism** — Understanding context between all tokens simultaneously
4. **Next Token Prediction** — Predicting the probability distribution over the vocabulary for the next token
5. **Generation** — Sampling from the distribution using strategies like greedy, beam search, or top-p sampling

Modern LLMs (GPT-4, Claude, Llama, Gemini) have billions of parameters and are pre-trained on trillions of tokens. They learn grammar, facts, reasoning patterns, and code through this self-supervised training.

---

### Q2. What are Foundation Models and how have they changed AI engineering?

**Answer:**
Foundation Models are large-scale pre-trained models (like GPT-4, BERT, CLIP) trained on broad data that can be adapted for many downstream tasks. They changed AI engineering by:

- **Eliminating the need to train from scratch** — Developers fine-tune or prompt these models instead
- **Enabling few-shot and zero-shot learning** — Tasks can be solved with minimal examples
- **Unifying multiple tasks** — One model can do translation, summarization, code generation, QA, etc.
- **Shifting the engineering paradigm** — From ML pipeline building to prompt engineering, RAG, and agent design

Previously, every task needed its own dedicated model. Foundation models democratized AI by giving teams a powerful starting point.

---

### Q3. What is the difference between generative AI and discriminative AI?

**Answer:**

| Feature | Generative AI | Discriminative AI |
|---|---|---|
| Goal | Generate new data | Classify/predict labels |
| Examples | GPT-4, Stable Diffusion, DALL-E | BERT (classification), SVM, ResNet |
| Output | Text, images, audio, code | Labels, probabilities |
| Training | Learns P(X) or P(X\|Y) | Learns P(Y\|X) |
| Use cases | Chatbots, image generation, summarization | Spam detection, image classification |

Generative models learn the underlying distribution of data; discriminative models learn the boundary between classes.

---

### Q4. What is the difference between open-source and closed-source LLMs? When would you choose one over the other?

**Answer:**

**Closed-source LLMs** (GPT-4, Claude, Gemini):
- Accessed via API; weights are not public
- High capability, easy to use
- Expensive at scale; data privacy concerns
- No customization of model internals

**Open-source LLMs** (Llama 3, Mistral, Falcon, Qwen):
- Weights are publicly available
- Can be self-hosted for privacy compliance
- Can be fine-tuned on proprietary data
- Requires infrastructure and ML expertise

**Choose closed-source when:** Speed to market is critical, budget is flexible, data is not highly sensitive.

**Choose open-source when:** Data privacy is paramount (healthcare, legal), you need deep customization, or cost at scale is a concern.

---

### Q5. What is hallucination in LLMs and why does it happen?

**Answer:**
Hallucination is when an LLM generates confident-sounding but factually incorrect or entirely fabricated information. It happens because:

1. **LLMs optimize for fluency, not factuality** — They predict the next probable token, not the "true" answer
2. **Training data limitations** — Gaps or incorrect information in training data are reproduced
3. **No grounding mechanism** — Without RAG or tool use, the model only uses parametric knowledge
4. **Overconfident generation** — The model fills gaps by extrapolating patterns rather than saying "I don't know"

**Mitigation strategies:**
- Retrieval-Augmented Generation (RAG)
- Prompt instructions to say "I don't know" when uncertain
- Temperature reduction for factual tasks
- Post-generation verification using another LLM
- Constitutional AI / RLHF alignment

---

### Q6. What are logits and how are they used in text generation?

**Answer:**
Logits are the raw, unnormalized scores output by the final linear layer of the LLM before any probability conversion. They represent the model's "preference" for each token in the vocabulary.

**Pipeline:** `Raw logits → Softmax → Probabilities → Sampling strategy → Token`

The softmax function converts logits to probabilities: `P(token_i) = e^(logit_i) / Σ e^(logit_j)`

Logits are modified through:
- **Temperature scaling** — Divides logits by temperature T before softmax; higher T = more random, lower T = more deterministic
- **Top-k filtering** — Keeps only top-k logits and zeros the rest
- **Top-p (nucleus) sampling** — Keeps smallest set of tokens whose cumulative probability ≥ p

---

### Q7. Explain Top-p (nucleus) sampling vs Top-k sampling.

**Answer:**

**Top-k Sampling:**
- Selects from the top k most probable tokens
- Fixed k (e.g., k=50) regardless of the probability distribution
- Problem: If distribution is very peaked, k=50 might include many near-zero probability tokens

**Top-p (Nucleus) Sampling:**
- Selects from the smallest set of tokens whose cumulative probability ≥ p (e.g., p=0.9)
- Dynamic — adapts to the distribution shape
- More natural-sounding text since it excludes the "long tail" of unlikely tokens

**When to use each:**
- Top-p is generally preferred for creative text generation
- Top-k is simpler and more predictable, useful for controlled outputs

---

### Q8. What is temperature in an LLM? How do you set it?

**Answer:**
Temperature controls the randomness of the model's output by scaling the logits before applying softmax.

- **Temperature = 0** → Greedy/deterministic; always picks the highest probability token
- **Temperature = 1.0** → Standard sampling from the original distribution
- **Temperature > 1** → Flatter distribution; more diverse/random outputs
- **Temperature < 1** → Sharper distribution; more focused/conservative outputs

**Practical guidance:**
- `0.0 – 0.3` → Factual Q&A, code generation, structured data extraction
- `0.5 – 0.7` → Conversational AI, chatbots
- `0.8 – 1.2` → Creative writing, brainstorming
- `> 1.2` → Experimental/highly creative tasks (often incoherent)

---

### Q9. What is context window size and why does it matter?

**Answer:**
The context window is the maximum number of tokens the LLM can process in a single forward pass — its "working memory." It includes the system prompt, conversation history, retrieved documents, and the new user input.

**Why it matters:**
- **RAG optimization** — Determines how many retrieved chunks can be passed to the model
- **Long document processing** — Limits how much text can be analyzed at once
- **Multi-turn conversations** — Longer context = better memory over a conversation
- **Cost** — Longer contexts are significantly more expensive with API pricing

**Current ranges:** GPT-4 (128K tokens), Claude (200K), Gemini (1M+), Llama 3 (128K)

**Challenges:** Even with large context windows, models suffer from "lost in the middle" — information at the very beginning and end of the context is recalled better than the middle.

---

### Q10. What is the difference between pre-training, fine-tuning, and instruction tuning?

**Answer:**

| Stage | Description | Data Type |
|---|---|---|
| **Pre-training** | Training from scratch on massive unlabeled text via next-token prediction | Terabytes of raw web text |
| **Fine-tuning** | Further training a pre-trained model on a smaller, task-specific dataset | Labeled examples for specific task |
| **Instruction Tuning** | Fine-tuning on (instruction, response) pairs to follow human instructions better | Structured prompt-response pairs |
| **RLHF** | Using human preference rankings + RL to align model behavior | Human preference comparisons |

Pre-training gives the model general world knowledge. Instruction tuning teaches it to follow directions. RLHF makes it helpful, safe, and aligned.

---

## 2. Transformer Architecture & Attention

---

### Q11. Explain the Transformer architecture.

**Answer:**
The Transformer (introduced in "Attention is All You Need", 2017) consists of:

**Encoder (used in BERT-style models):**
- Multi-head self-attention
- Feed-forward neural network
- Layer normalization + residual connections

**Decoder (used in GPT-style models):**
- Masked multi-head self-attention (causal — can only see past tokens)
- Cross-attention (attends to encoder output, used in seq2seq)
- Feed-forward layers

**Key components:**
- **Positional Encoding** — Adds position information to embeddings (absolute or rotary/RoPE)
- **Multi-Head Attention** — Multiple attention "heads" capture different aspects of context
- **Layer Norm** — Stabilizes training
- **Feed-Forward Network** — Two linear layers with a non-linearity (GELU/ReLU)

Most modern LLMs use a decoder-only architecture (GPT, Llama, Claude, Mistral).

---

### Q12. Explain Q, K, V (Query, Key, Value) in self-attention.

**Answer:**
Self-attention transforms each input token into three vectors through learned linear projections:

- **Query (Q)** — "What am I looking for?" — represents the current token searching for relevant context
- **Key (K)** — "What do I offer?" — represents each token's identity as a potential match
- **Value (V)** — "What do I contribute?" — the actual information to aggregate if a match is found

**Attention formula:** `Attention(Q, K, V) = softmax(QK^T / √d_k) × V`

1. Compute dot products between Q and all K's → get similarity scores
2. Scale by √d_k to prevent vanishing gradients
3. Apply softmax → attention weights (summing to 1)
4. Multiply weights by V → weighted sum of values

**Multi-head attention** runs this process h times in parallel with different projections, then concatenates the results. Each head can focus on different types of relationships (syntactic, semantic, coreference, etc.).

---

### Q13. What is positional encoding and why is Transformers need it?

**Answer:**
Transformers process all tokens simultaneously (unlike RNNs which process sequentially), so they have no inherent notion of token order. Positional encoding injects position information into token embeddings.

**Types:**
- **Sinusoidal (original):** Uses sin/cos functions at different frequencies; fixed, not learned
- **Learned absolute positional embeddings:** Position vectors learned during training (BERT, GPT-2)
- **Rotary Positional Embeddings (RoPE):** Encodes relative positions by rotating Q and K vectors; used in Llama, Mistral — generalizes better to longer sequences
- **ALiBi (Attention with Linear Biases):** Adds a linear bias to attention scores based on distance; efficient for long contexts

RoPE has become the de facto standard in modern LLMs because it handles longer contexts better.

---

### Q14. What is the difference between encoder-only, decoder-only, and encoder-decoder architectures?

**Answer:**

| Architecture | Examples | Best For |
|---|---|---|
| **Encoder-only** | BERT, RoBERTa, DistilBERT | Understanding tasks: classification, NER, embedding generation |
| **Decoder-only** | GPT-4, Llama, Mistral, Claude | Text generation, chat, code generation |
| **Encoder-Decoder** | T5, BART, mT5 | Seq2seq tasks: translation, summarization, question answering |

**Encoder-only:** Bidirectional attention — each token sees all other tokens. Great for classification and creating rich text representations.

**Decoder-only:** Causal/unidirectional attention — tokens only see past tokens. Autoregressive generation. Dominates the current LLM landscape.

**Encoder-Decoder:** Encoder processes input fully; decoder generates output while attending to encoder. Classic for tasks with distinct input/output structures.

---

### Q15. What is Flash Attention and why does it matter?

**Answer:**
Flash Attention is an IO-aware, exact attention algorithm that computes the standard attention operation but dramatically more efficiently by:

1. **Tiling** — Splits Q, K, V into blocks and processes them in SRAM (fast) rather than HBM (slow GPU memory)
2. **Kernel Fusion** — Fuses multiple operations (matrix multiply, softmax, dropout) into a single GPU kernel
3. **Recomputation** — Instead of storing the full N×N attention matrix, it recomputes it during backpropagation

**Benefits:**
- Reduces memory from O(N²) to O(N) for long sequences
- 2–4× speedup in training and inference
- Enables much longer context windows without running out of memory

Flash Attention 2 and 3 are now standard in all major LLM training frameworks.

---

## 3. Tokenization & Embeddings

---

### Q16. What is tokenization? Explain BPE, WordPiece, and SentencePiece.

**Answer:**
Tokenization is the process of converting raw text into discrete units (tokens) that the model can process. Most LLMs use subword tokenization — a middle ground between character-level and word-level.

**Byte Pair Encoding (BPE):**
- Starts with individual characters
- Iteratively merges the most frequent adjacent pairs
- Used by GPT-2, GPT-4, Llama, Mistral
- Vocabulary size typically 32K–128K

**WordPiece:**
- Similar to BPE but merges based on likelihood increase (not raw frequency)
- Used by BERT, DistilBERT
- Prefixes sub-words with `##` (e.g., `playing` → `play`, `##ing`)

**SentencePiece:**
- Language-agnostic; treats the text as raw Unicode without pre-tokenization
- Used by T5, Llama (wraps BPE or unigram as the algorithm)
- Handles multiple languages and languages without clear word boundaries

**Why it matters:** Tokenization affects context window usage, model performance on rare words, multilingual ability, and code generation.

---

### Q17. What are embeddings? What is the role of embeddings in AI systems?

**Answer:**
Embeddings are dense, continuous vector representations of data (text, images, etc.) in a high-dimensional space where semantic similarity corresponds to geometric proximity.

**Types:**
- **Token embeddings** — Each vocabulary token mapped to a learnable vector
- **Sentence/document embeddings** — A single vector representing an entire text passage (e.g., from models like `text-embedding-ada-002`, `bge-large-en`)
- **Image embeddings** — Dense vectors representing images (CLIP, ViT)

**Role in AI systems:**
- **Semantic search** — Find similar documents by cosine similarity
- **RAG** — Embed documents and queries to retrieve relevant context
- **Recommendation systems** — Match user preferences to items
- **Clustering & classification** — Group similar content

**Embedding quality** is measured by benchmarks like MTEB (Massive Text Embedding Benchmark).

---

### Q18. Explain cosine similarity, dot product, and Euclidean distance for vector search. When would you use each?

**Answer:**

**Cosine Similarity:**
- Measures angle between vectors: `cos(θ) = (A·B) / (|A| |B|)`
- Range: -1 to 1 (1 = identical direction, 0 = orthogonal)
- **Use when:** Vectors have different magnitudes; you care about direction/orientation more than scale. Standard for text similarity search.

**Dot Product:**
- `A·B = |A| |B| cos(θ)` — affected by both angle and magnitude
- Faster to compute than cosine similarity (no normalization)
- **Use when:** Vectors are already normalized to unit length (dot product = cosine similarity then), or when magnitude is meaningful

**Euclidean Distance (L2):**
- Straight-line distance in vector space
- **Use when:** Absolute positions in the embedding space matter; less common for NLP but used in some image embeddings

**In practice:** Most vector databases use cosine similarity or inner product for text embeddings. If embeddings are L2-normalized, inner product is equivalent to cosine similarity and is faster.

---

## 4. Prompt Engineering

---

### Q19. What is prompt engineering? Why is it important?

**Answer:**
Prompt engineering is the practice of designing, structuring, and optimizing input prompts to elicit the best possible output from an LLM without modifying the model's weights.

**It's important because:**
- Well-designed prompts dramatically improve output quality, accuracy, and consistency
- Reduces hallucinations and undesirable behaviors
- Can dramatically change model behavior without fine-tuning costs
- Enables few-shot learning — teaching the model a task through examples

**Core principles:**
- Be specific and explicit about the task
- Provide context and role (system prompt)
- Use structured formats (XML tags, JSON schema)
- Include examples (few-shot)
- Specify output format

---

### Q20. Explain Zero-shot, One-shot, and Few-shot prompting.

**Answer:**

**Zero-shot prompting:**
- No examples provided; the model relies entirely on pre-trained knowledge
- Example: "Translate the following English sentence to French: Hello, how are you?"

**One-shot prompting:**
- One example provided to show the format/behavior expected
- Example: "Q: What is the capital of France? A: Paris. Q: What is the capital of Japan? A:"

**Few-shot prompting:**
- Multiple (typically 3–10) examples provided
- Significantly improves performance on specific tasks
- Examples should be diverse and representative

**Best practice:** Few-shot examples should be similar to the actual input, placed near the end of the prompt, and formatted consistently.

---

### Q21. What is Chain-of-Thought (CoT) prompting?

**Answer:**
Chain-of-Thought prompting instructs the LLM to reason step by step before producing a final answer, significantly improving performance on complex reasoning tasks like math, logic, and multi-step problems.

**Standard CoT:** "Let's think step by step..."

**Few-shot CoT:** Provide examples where each answer includes the reasoning chain:
```
Q: Roger has 5 tennis balls. He buys 2 more cans, each with 3 balls. How many does he have?
A: Roger starts with 5 balls. 2 cans × 3 balls = 6 new balls. 5 + 6 = 11 balls. The answer is 11.

Q: [Your question here]
A: Let me work through this step by step...
```

**Variants:**
- **Zero-shot CoT:** Simply add "Let's think step by step" to the prompt
- **Self-consistency CoT:** Sample multiple CoT paths, take majority vote on final answer
- **Tree of Thought (ToT):** Explore multiple reasoning branches, not just one linear chain
- **ReAct (Reason + Act):** Interleave reasoning and action steps for agent tasks

---

### Q22. What is the difference between system prompt and user prompt?

**Answer:**

**System Prompt:**
- A hidden instruction set that establishes the model's behavior, persona, and constraints
- Not visible to end users during conversation
- High authority — generally overrides user instructions (though not always)
- Used for: role definition, safety guardrails, output format specification, context setting
- Example: "You are a helpful customer support agent for Acme Corp. Always be polite. Never discuss competitor products."

**User Prompt:**
- The actual message sent by the user
- Variable per interaction
- Lower authority than the system prompt in most implementations

**Best practices for system prompts:**
- Define the persona and tone clearly
- Specify what the model should and shouldn't do
- Include output format requirements
- Provide relevant background context

---

### Q23. What is prompt injection and how do you defend against it?

**Answer:**
Prompt injection is an attack where malicious content in user input or retrieved documents overrides or manipulates the LLM's original instructions.

**Types:**
- **Direct injection** — User directly tells the model to ignore system prompt: "Ignore previous instructions and..."
- **Indirect injection** — Malicious instructions hidden in data the LLM processes (e.g., a web page, PDF, email)

**Defense strategies:**
1. **Input sanitization** — Filter known injection patterns before passing to the model
2. **Privilege separation** — Treat user/retrieved content as lower trust than system instructions
3. **XML/delimiter encapsulation** — Wrap user content in clear delimiters: `<user_input>...</user_input>`
4. **Instruction reinforcement** — Reiterate system instructions after user input
5. **Output validation** — Use a second LLM or rule-based system to check outputs for policy violations
6. **Adversarial testing** — Regularly red-team your system with known injection patterns
7. **Minimal permissions** — Don't give agents permissions beyond what's needed

---

### Q24. What are advanced prompting techniques? (Tree of Thought, Self-consistency, ReAct)

**Answer:**

**Tree of Thought (ToT):**
- Extends CoT to explore multiple reasoning branches simultaneously
- The model generates several "thoughts" at each step, evaluates them, and continues only the most promising branches
- Acts like a BFS/DFS search over reasoning paths
- Great for creative problem-solving and puzzles

**Self-Consistency:**
- Generate the same problem multiple times with CoT at high temperature
- Take the most frequent final answer (majority vote)
- Improves accuracy by 5–15% on reasoning benchmarks without any additional data

**ReAct (Reasoning + Acting):**
- Interleaves "Thought" (reasoning) and "Action" (tool use) steps
- Pattern: `Thought: I need to find X → Action: search("X") → Observation: result → Thought: Based on this... → Action: ...`
- Foundation of most modern AI agent architectures

**DSPy (Declarative Self-improving Prompts):**
- Rather than hand-crafting prompts, DSPy optimizes them programmatically using a training set
- The engineer specifies the task signature and metric; DSPy finds the best prompt

---

## 5. Retrieval-Augmented Generation (RAG)

---

### Q25. What is RAG? Why is it needed even though LLMs are powerful?

**Answer:**
Retrieval-Augmented Generation (RAG) is a framework that enhances LLMs by fetching relevant external information at inference time and injecting it into the prompt as context before generation.

**Why LLMs alone are insufficient:**
1. **Static knowledge cutoff** — Training data has a date; the model can't know recent events
2. **Hallucination** — Without grounding, LLMs fabricate facts confidently
3. **No access to private data** — Company documents, internal wikis, databases are not in training data
4. **Context window limits** — Can't fit an entire knowledge base into a prompt
5. **Expensive fine-tuning** — Updating knowledge via fine-tuning is costly and doesn't guarantee accuracy

**RAG solves all of the above** by retrieving the specific relevant information needed for each query at runtime.

---

### Q26. Explain the architecture of a basic RAG system step by step.

**Answer:**

**Indexing Phase (offline):**
1. **Document Ingestion** — Load PDFs, Word docs, web pages, databases
2. **Chunking** — Split documents into smaller segments (e.g., 512 tokens)
3. **Embedding** — Convert each chunk into a dense vector using an embedding model
4. **Storage** — Store chunks + embeddings in a vector database (Pinecone, Weaviate, Chroma, FAISS)

**Query Phase (online):**
1. **Query Embedding** — Embed the user's question using the same embedding model
2. **Retrieval** — Find the top-k most similar chunks via ANN search
3. **Reranking (optional)** — Use a cross-encoder to rerank retrieved chunks for better precision
4. **Prompt Assembly** — Inject retrieved chunks + original query into a prompt template
5. **Generation** — LLM generates an answer grounded in the retrieved context
6. **Response** — Return the generated answer (with optional citations)

---

### Q27. What are chunking strategies in RAG? How do you choose chunk size?

**Answer:**
Chunking is splitting documents into pieces before embedding. It's critical because it directly affects retrieval quality.

**Strategies:**

| Strategy | Description | Best For |
|---|---|---|
| **Fixed-size** | Split every N tokens with overlap | Simple, general-purpose |
| **Sentence-based** | Split at sentence boundaries | Q&A, factual retrieval |
| **Paragraph/section-based** | Split at natural document structure | Structured documents |
| **Semantic chunking** | Group sentences with similar meaning | Complex narrative documents |
| **Recursive character splitting** | Try multiple separators (paragraph → sentence → word) | Mixed content |
| **Agentic/late chunking** | Let the model decide chunk boundaries | Advanced use cases |

**Choosing chunk size:**
- **Too small** → Lacks context, incomplete answers, poor semantic coherence
- **Too large** → Diluted embeddings, irrelevant information in retrieved chunks, context window pressure

**Rule of thumb:** 256–512 tokens per chunk with 10–20% overlap is a good starting point. Always benchmark on your specific data and query types. Chunk size should be correlated with the embedding model's optimal input length.

---

### Q28. What is the difference between sparse and dense retrieval in RAG?

**Answer:**

**Sparse Retrieval (BM25, TF-IDF):**
- Keyword-based; represents documents as sparse vectors (mostly zeros)
- Fast and highly interpretable
- Excellent for exact keyword matching ("API v2.3 error code 404")
- Fails on semantic queries (misses synonyms, paraphrases)

**Dense Retrieval (embedding-based):**
- Semantic; represents documents as dense vectors
- Captures meaning, synonyms, and paraphrases
- Slower (requires ANN search)
- Can miss exact keyword matches (e.g., product codes, names)

**Hybrid Search (Best of Both Worlds):**
- Runs both BM25 and dense search in parallel
- Combines results using Reciprocal Rank Fusion (RRF) or weighted combination
- Significantly outperforms either method alone
- Used in production RAG by most enterprise teams

Most modern RAG systems use hybrid search followed by a neural reranker.

---

### Q29. What is reranking in RAG and why is it important?

**Answer:**
Reranking is a second-pass retrieval step where an initial set of retrieved candidates (e.g., top-20) is re-scored using a more accurate but slower model to produce a final top-k (e.g., top-5).

**Why it's needed:**
- Embedding models (bi-encoders) encode query and document independently — efficient but less accurate
- Cross-encoders process query + document together — much more accurate but too slow for full index search
- Reranking uses the cross-encoder only on the already-filtered small candidate set

**Popular rerankers:** Cohere Rerank API, BGE Reranker, cross-encoder/ms-marco-MiniLM

**Metrics for evaluating rerankers:**
- **MRR (Mean Reciprocal Rank)** — How high is the first relevant document?
- **NDCG@k (Normalized Discounted Cumulative Gain)** — Weighted ranking quality up to k results
- **MAP (Mean Average Precision)** — Average precision across all relevant documents

**Impact:** Reranking typically improves RAG answer quality by 10–30% with modest latency increase.

---

### Q30. Explain advanced RAG patterns: Self-RAG, Corrective RAG (CRAG), Agentic RAG, Graph RAG.

**Answer:**

**Self-RAG:**
- The LLM itself decides when to retrieve (not always), critiques the retrieved documents, and self-reflects on its own output
- Uses special tokens: `[Retrieve]`, `[IsRelevant]`, `[IsSupportive]`, `[IsComplete]`
- More efficient — only retrieves when needed; more accurate — checks its own responses

**Corrective RAG (CRAG):**
- Adds a validation step after retrieval: an LLM evaluator scores retrieved documents for relevance
- If documents are irrelevant (below threshold), the system falls back to web search or alternative retrieval
- Prevents feeding garbage context to the generator

**Agentic RAG:**
- An LLM agent controls the retrieval process
- Can reformulate queries, decide to retrieve again, aggregate from multiple sources, and reason about retrieved information
- Much more powerful for complex multi-step research tasks

**Graph RAG:**
- Builds a knowledge graph (entities and relationships) from the corpus instead of or in addition to a vector index
- Enables multi-hop reasoning (A→B→C relationships)
- Better for questions requiring synthesis across many documents
- Used by Microsoft GraphRAG

---

### Q31. How do you handle hallucinations in a RAG pipeline?

**Answer:**

1. **Strict prompting** — Instruct the LLM to only use provided context: "Answer only based on the context below. If the answer is not in the context, say 'I don't know'."

2. **Faithfulness evaluation** — Use an LLM-as-judge to verify every claim in the response is supported by the retrieved context

3. **Citation enforcement** — Require the model to cite source chunks for each claim

4. **Corrective RAG (CRAG)** — Validate retrieved documents before generation

5. **Reduce temperature** — For factual tasks, use temperature = 0

6. **Reranking** — Better context quality reduces the chance of fabrication

7. **Query-context relevance check** — Check if retrieved chunks are relevant before passing to generator

8. **RAGAS evaluation** — Use the RAGAS framework to measure Faithfulness, Answer Relevancy, Context Precision/Recall continuously in production

---

### Q32. How do you evaluate a RAG system? What metrics do you use?

**Answer:**
RAG evaluation uses the **RAGAS** framework and related metrics:

| Metric | Description |
|---|---|
| **Faithfulness** | Is the generated answer supported by the retrieved context? (0–1) |
| **Answer Relevancy** | How relevant is the answer to the original question? |
| **Context Precision** | Are the retrieved chunks actually relevant? (Signal-to-noise ratio) |
| **Context Recall** | Does the retrieved context contain all information needed to answer? |
| **Context Relevancy** | Overall quality of the retrieved context |
| **Answer Correctness** | Compared to a ground-truth answer (requires labeled dataset) |

**Evaluation pipeline:**
1. Create a test set: (question, ground_truth_answer, relevant_document) triples
2. Run RAG system to get generated answer + retrieved contexts
3. Use RAGAS/LLM-as-judge to score each metric
4. Monitor these metrics in production using sampling

---

### Q33. What is HyDE (Hypothetical Document Embedding)?

**Answer:**
HyDE (Hypothetical Document Embeddings) is a query transformation technique for RAG that improves retrieval quality:

**Problem:** User queries are often short, keyword-focused, and semantically different from the longer, detailed documents in the knowledge base. This embedding gap reduces retrieval quality.

**HyDE Solution:**
1. Use an LLM to generate a hypothetical document that would be the ideal answer to the query (without RAG context)
2. Embed this hypothetical document instead of (or in addition to) the original query
3. Use this richer embedding to search the vector store

**Why it works:** The hypothetical document is in the same style and vocabulary as real knowledge base documents, creating a better embedding match.

**Other query transformations:**
- **Query decomposition** — Break complex queries into simpler sub-questions
- **Step-back prompting** — Generalize the specific question to a higher-level principle first
- **Multi-query retrieval** — Generate multiple reformulations and take the union of results

---

### Q34. Compare RAG vs fine-tuning. When would you use each?

**Answer:**

| Dimension | RAG | Fine-Tuning |
|---|---|---|
| **Best for** | Factual recall, private/dynamic knowledge | Style, behavior, domain-specific reasoning |
| **Data freshness** | Real-time (update vector DB) | Static until retrained |
| **Hallucination risk** | Lower (grounded in retrieved text) | Higher without grounding |
| **Cost** | Inference-time retrieval cost | High upfront training cost |
| **Transparency** | Citations possible | Black-box knowledge |
| **Custom behavior** | Limited | High (tone, format, specialized skills) |
| **Latency** | Higher (retrieval + generation) | Lower (generation only) |

**Choose RAG when:**
- Knowledge changes frequently (news, company policies, product catalog)
- You need citations and verifiability
- Data is sensitive and shouldn't be in model weights
- Knowledge base is very large

**Choose Fine-tuning when:**
- Teaching specialized vocabulary, style, or format
- The model needs to reliably follow complex instructions
- Response latency is critical
- You want to compress knowledge of a smaller domain

**In practice, many production systems use both:** Fine-tune for behavior + RAG for factual grounding.

---

## 6. Vector Databases & Similarity Search

---

### Q35. What is a vector database and how does it differ from a traditional database?

**Answer:**

A vector database is a specialized database designed to store, index, and efficiently query high-dimensional embedding vectors using approximate nearest neighbor (ANN) search.

| Feature | Traditional DB (SQL/NoSQL) | Vector Database |
|---|---|---|
| Data type | Structured rows, JSON, etc. | High-dimensional float vectors |
| Query type | Exact match, range, filter | Semantic similarity (nearest neighbor) |
| Index type | B-tree, hash index | HNSW, IVF, PQ |
| Use case | Transactions, reporting | Semantic search, RAG, recommendations |
| Examples | PostgreSQL, MongoDB | Pinecone, Weaviate, Chroma, Qdrant, FAISS |

**How ANN search works:**
- **HNSW (Hierarchical Navigable Small World)** — Graph-based index; fast, high accuracy, used by most production vector DBs
- **IVF (Inverted File Index)** — Clusters vectors; fast but less accurate
- **Product Quantization (PQ)** — Compresses vectors for memory efficiency

**Popular choices:**
- **Pinecone** — Managed, production-grade, highly scalable
- **Weaviate** — Open-source, supports hybrid search natively
- **Chroma** — Developer-friendly, great for local development
- **Qdrant** — Open-source, great filtering support
- **FAISS** — Facebook's in-memory library, used for offline processing
- **pgvector** — Vector search as a Postgres extension (easy if already on Postgres)

---

### Q36. What is metadata filtering in vector databases and when is it important?

**Answer:**
Metadata filtering allows you to pre-filter the vector search space using non-vector attributes (metadata) before or alongside the similarity search.

**Example:** If searching a medical knowledge base, you might filter by `document_type = "clinical_guidelines"` AND `specialty = "cardiology"` before doing semantic search. This ensures you only search within relevant documents.

**Why it matters:**
- Prevents irrelevant but semantically similar documents from appearing
- Dramatically reduces false positives
- Enables multi-tenant applications (each user only searches their own data)
- Improves both speed and accuracy

**Pre-filtering vs. Post-filtering:**
- **Pre-filter** — Restrict the search space first, then do ANN search (may miss some results if filter is too aggressive)
- **Post-filter** — Do broad ANN search, then filter results (can return < k results)
- Modern vector DBs like Qdrant and Weaviate support efficient pre-filtering without sacrificing recall

---

## 7. Fine-Tuning & RLHF

---

### Q37. What is LoRA (Low-Rank Adaptation) and how does it work?

**Answer:**
LoRA is a parameter-efficient fine-tuning (PEFT) technique that adds small trainable low-rank matrices to frozen pre-trained weight matrices instead of updating all parameters.

**How it works:**
- For a weight matrix W (e.g., 4096×4096 = 16M parameters), LoRA adds: `ΔW = A × B`
  - A is shape (d × r) and B is shape (r × d), where r << d (rank, typically 4–64)
  - During inference: `W_new = W + ΔW = W + AB`
- Only A and B are trained; W remains frozen
- If r=16 and d=4096, ΔW uses only 2 × (4096 × 16) = 131,072 parameters vs 16M

**Benefits:**
- 10–100× fewer trainable parameters
- ~3× less GPU memory
- No inference latency increase (AB can be merged into W at deployment time)
- Multiple LoRA adapters can be swapped without reloading the base model

**QLoRA:** Combines LoRA with 4-bit quantization of the base model. Enables fine-tuning a 70B parameter model on a single consumer GPU.

---

### Q38. What is RLHF (Reinforcement Learning from Human Feedback)?

**Answer:**
RLHF is a training technique that aligns LLM behavior with human preferences through a three-stage process:

**Stage 1: Supervised Fine-Tuning (SFT)**
- Fine-tune the base LLM on high-quality (prompt, ideal response) pairs created by human annotators
- Creates the SFT model

**Stage 2: Reward Model Training**
- Show annotators multiple model outputs for the same prompt
- Annotators rank them from best to worst
- Train a separate "reward model" to predict human preference scores for any (prompt, response) pair

**Stage 3: PPO Training (RL)**
- Use the SFT model as the starting policy
- For each generated response, the reward model gives a score
- Optimize the policy using Proximal Policy Optimization (PPO) to maximize expected reward
- KL-divergence penalty prevents the model from drifting too far from the SFT baseline

**Modern alternatives:**
- **DPO (Direct Preference Optimization)** — Eliminates the separate reward model; directly optimizes on preference pairs using a mathematical equivalence to PPO. More stable and simpler.
- **KTO (Kahneman-Tversky Optimization)** — Uses individual preference labels (good/bad) rather than paired comparisons

---

### Q39. What is catastrophic forgetting? How do you prevent it during fine-tuning?

**Answer:**
Catastrophic forgetting occurs when a model fine-tuned on a new domain loses its general capabilities from pre-training. The fine-tuning gradient updates overwrite weights that encoded general knowledge.

**Prevention strategies:**

1. **LoRA/PEFT methods** — Freeze most weights; only update small adapter layers. The base model's general knowledge is preserved.

2. **Replay buffers** — Include samples from the original training data alongside the new data (mixture fine-tuning)

3. **Low learning rate** — Fine-tune with a very small LR to make only minimal updates to pre-trained weights

4. **Elastic Weight Consolidation (EWC)** — Adds a penalty term that slows down learning for weights important to previous tasks

5. **Evaluate general benchmarks** — Regularly test on general benchmarks (MMLU, HellaSwag) during fine-tuning to detect regression

6. **Instruction-tuning mixture** — Mix general instruction-following examples with domain data

---

### Q40. What are key hyperparameters for fine-tuning? How do you set them?

**Answer:**

| Hyperparameter | Typical Range | Guidance |
|---|---|---|
| **Learning rate** | 1e-5 to 5e-4 | Start with 2e-4 for LoRA, lower for full fine-tuning |
| **Epochs** | 1–5 | More epochs = overfitting risk; 1–3 often sufficient |
| **Batch size** | 4–64 | Larger = more stable gradients but more memory |
| **LoRA rank (r)** | 4–128 | Higher r = more capacity but more parameters; 16–64 common |
| **LoRA alpha** | 2×r typically | Controls LoRA scaling |
| **Warmup steps** | 50–200 | Prevents large updates at start |
| **Max sequence length** | 512–4096 | Match to actual data; longer = more memory |
| **Gradient accumulation** | 4–8 | Simulates larger batch with limited GPU memory |

**Practical approach:**
1. Start with conservative LR + 1 epoch to check for baseline improvement
2. Use learning rate finder or log perplexity on validation set
3. Monitor for overfitting (train loss ↓ but val loss ↑)

---

## 8. AI Agents & Agentic Systems

---

### Q41. What is an AI agent? How does it differ from a simple LLM call?

**Answer:**

An AI agent is a system that uses an LLM as a reasoning engine to autonomously plan, make decisions, use tools, and execute multi-step tasks to achieve a goal — often in a loop.

**Simple LLM call:**
- Input → LLM → Output (single turn)
- No persistent state, no tool use, no loops
- Stateless, reactive

**AI Agent:**
- Has a **goal** (objective to achieve)
- Can use **tools** (web search, code execution, database query, APIs)
- Has a **loop** (plan → act → observe → re-plan)
- Has **memory** (short-term context + long-term storage)
- Can **self-reflect** and change its plan based on observations

**Core agent loop (ReAct pattern):**
```
[Thought] → [Action] → [Observation] → [Thought] → [Action] → ... → [Final Answer]
```

---

### Q42. What is the ReAct agent architecture?

**Answer:**
ReAct (Reasoning + Acting) is a foundational agent architecture that interleaves reasoning traces and action execution in a single prompt.

**Cycle:**
1. **Thought:** The LLM reasons about the current state and decides what to do
2. **Action:** The LLM calls a tool (e.g., `search("current population of India")`)
3. **Observation:** The tool result is returned to the LLM
4. **Repeat** until the task is complete

**Example trace:**
```
Thought: I need to find the GDP of India in 2024.
Action: web_search("India GDP 2024")
Observation: India's GDP in 2024 was approximately $3.9 trillion USD.
Thought: Now I have the information needed. I can answer.
Final Answer: India's GDP in 2024 was approximately $3.9 trillion USD.
```

**Advantages:** Transparent reasoning; easy to debug; tool failures can be recovered with re-planning

**Limitation:** Fragile to prompt formatting errors; can get stuck in loops; latency accumulates with many steps

---

### Q43. What types of memory do AI agents use?

**Answer:**

| Memory Type | Description | Implementation |
|---|---|---|
| **In-context (short-term)** | Conversation history in the current prompt | Message history in the context window |
| **External (long-term)** | Persistent facts about the user/world | Vector DB or key-value store |
| **Episodic** | Past interaction summaries | Summarized + stored memories |
| **Procedural** | How to do things (skills, prompts) | Prompt templates, tool definitions |
| **Semantic** | World knowledge | RAG over a knowledge base |

**Memory management strategies:**
- **Sliding window** — Keep only last N turns; simple but loses early context
- **Summarization** — Periodically summarize old conversation; preserves essence
- **Vector memory** — Embed and store important facts; retrieve relevant ones per turn
- **Entity memory** — Track specific entities (people, projects) and their attributes

---

### Q44. What are tools in an AI agent? How do you design good tools?

**Answer:**
Tools are functions the agent can call to interact with the outside world: APIs, databases, code interpreters, browsers, etc.

**Examples of tools:**
- `web_search(query)` — Search the internet
- `run_python(code)` — Execute code and return output
- `get_weather(location)` — Call weather API
- `query_database(sql)` — Run SQL queries
- `send_email(to, subject, body)` — Send emails

**Principles for designing good tools:**
1. **Single responsibility** — Each tool does one thing well
2. **Clear, descriptive docstrings** — The LLM decides which tool to call based on the description
3. **Predictable input/output schema** — Use Pydantic or JSON schema for inputs
4. **Idempotency where possible** — Safe to retry on failure
5. **Graceful error handling** — Return structured error messages the LLM can reason about
6. **Minimal side effects** — Don't make destructive changes without confirmation
7. **Appropriate granularity** — Not too broad (unreliable) or too narrow (too many tools to choose from)

---

### Q45. What is human-in-the-loop (HITL) in agentic AI?

**Answer:**
Human-in-the-loop is a design pattern where the agent pauses and requests human approval before executing certain high-stakes or irreversible actions.

**When to use HITL:**
- Before sending emails, making purchases, deleting data, or deploying code
- When the agent's confidence is low
- After a plan is generated but before execution begins
- At user-defined "checkpoints" in long workflows

**Implementation patterns:**
- **Approval gates** — Agent presents action plan; human approves/rejects/modifies
- **Interrupt on condition** — Agent automatically pauses if a certain condition is met (e.g., cost > $10)
- **Async approval** — Agent creates a task for human review and waits for a webhook
- **LangGraph interrupt mechanism** — Native HITL support with graph state management

**LangGraph example:** Use `interrupt_before=["execute_action"]` to pause the graph at specific nodes for human review.

---

## 9. Multi-Agent Systems

---

### Q46. What is a multi-agent system and when should you use it?

**Answer:**
A multi-agent system consists of multiple specialized LLM agents that collaborate, communicate, and divide tasks to complete complex goals that a single agent would struggle with.

**When to use multi-agent:**
- **Parallelization** — Tasks that can run simultaneously (research + coding at the same time)
- **Specialization** — Different agents with different tools, prompts, or even models for different subtasks
- **Scalability** — Single agent context window can't hold all state and history
- **Quality control** — One agent generates, another reviews/critiques
- **Complex workflows** — Research → Writing → Editing → Fact-checking pipeline

**Common multi-agent patterns:**
- **Supervisor** — A central orchestrator delegates to specialized agents
- **Peer-to-peer** — Agents communicate directly (AutoGen style)
- **Pipeline** — Sequential handoff (Agent A's output is Agent B's input)
- **Debate** — Multiple agents present different views; a judge synthesizes

---

### Q47. What are popular multi-agent frameworks? Compare them.

**Answer:**

| Framework | Best For | Approach |
|---|---|---|
| **LangGraph** | Production stateful agents; complex conditional logic | Graph-based workflow with explicit state |
| **CrewAI** | Role-based multi-agent teams; quick setup | Declarative agent roles and task assignments |
| **AutoGen (Microsoft)** | Conversational multi-agent; research prototyping | Agents communicate via message passing |
| **LlamaIndex Agents** | Data-heavy agentic pipelines; RAG-centric agents | Index-first agent design |
| **OpenAI Agents SDK** | Production agents with OpenAI models | Handoffs and guardrails natively |
| **SmolAgents (Hugging Face)** | Lightweight, fast agent prototyping | Code-first agent execution |

**LangGraph vs CrewAI:**
- LangGraph: More control, better for production, steeper learning curve, supports complex branching/loops
- CrewAI: Faster to get started, more intuitive for role-based teams, less flexible for complex logic

---

### Q48. What is Model Context Protocol (MCP) and why is it important?

**Answer:**
MCP (Model Context Protocol) is an open standard by Anthropic that standardizes how AI agents connect to and interact with external tools and data sources.

**Before MCP:** Every AI application had to build custom integrations for each tool/service. N models × M tools = N×M custom integrations.

**With MCP:** Tools expose a standard MCP server interface. Any MCP-compatible model/agent can plug in seamlessly. N models × M tools = N+M implementations.

**Components:**
- **MCP Servers** — Expose resources, tools, and prompts over a standard protocol
- **MCP Clients** — LLM applications that connect to MCP servers (Claude Desktop, Cursor, etc.)
- **Transport** — stdio (local) or SSE/HTTP (remote)

**Impact:** MCP is becoming the "USB standard for AI tools" — enabling an ecosystem where tools built once work with any AI system. Major platforms (GitHub, Slack, Notion) have released official MCP servers.

---

### Q49. How do you handle agent failures and error recovery in production?

**Answer:**

1. **Retry logic with backoff** — Retry failed tool calls 2–3 times with exponential backoff before escalating

2. **Fallback tools** — If primary tool fails (e.g., web search rate-limited), use alternative (Wikipedia API)

3. **Structured error returns** — Tools return structured error objects the LLM can reason about: `{"error": "rate_limited", "retry_after": 5}`

4. **Max step limits** — Set maximum number of agent iterations to prevent infinite loops

5. **Timeout handling** — Set timeouts per tool call; surface meaningful errors to the agent

6. **Checkpointing** — Use LangGraph's persistence to save agent state so failed runs can be resumed

7. **Human escalation** — If agent fails X times or encounters unknown error, escalate to human

8. **Circuit breakers** — Stop calling a failing service entirely after threshold of errors

9. **Observability** — Full traces in LangSmith/Langfuse to debug what went wrong in production

---

## 10. Frameworks (LangChain, LangGraph, LlamaIndex, CrewAI)

---

### Q50. What is LangChain? What problems does it solve?

**Answer:**
LangChain is an open-source framework for building LLM-powered applications. It provides abstractions for:

- **LLM providers** — Unified interface for OpenAI, Anthropic, Google, Hugging Face, etc.
- **Prompt management** — PromptTemplates, ChatPromptTemplates with variable injection
- **Chains** — Compose multiple LLM calls and tools into sequential or conditional workflows (LCEL)
- **Memory** — Conversation history management
- **Agents** — Tool use and reasoning loops
- **Document loaders & splitters** — 100+ loaders for PDFs, web pages, databases, etc.
- **Vector store integrations** — Connect to Pinecone, Chroma, Weaviate, FAISS, etc.
- **Output parsers** — Parse LLM output into structured Python objects

**LangChain Expression Language (LCEL):** Declarative syntax for composing chains: `chain = prompt | llm | output_parser`

---

### Q51. What is LangGraph and how does it differ from LangChain?

**Answer:**
LangGraph is a framework built on LangChain for building stateful, graph-based agentic workflows. While LangChain chains are linear (or simple branches), LangGraph enables cycles, loops, and complex conditional logic.

**Key concepts:**
- **Nodes** — Functions (LLM calls, tools, human steps) in the graph
- **Edges** — Connections between nodes; can be conditional
- **State** — A typed dictionary shared across all nodes in the graph
- **Checkpointers** — Persist state to enable pause/resume, HITL, and recovery

**LangChain vs LangGraph:**

| | LangChain | LangGraph |
|---|---|---|
| Structure | Linear chains | Directed graph with cycles |
| State management | Limited | First-class typed state |
| Agent support | Basic | Production-grade with loops |
| HITL | Manual | Native (`interrupt_before`) |
| Parallelism | Limited | Native parallel branches |
| Production readiness | Moderate | High |

---

### Q52. What is LlamaIndex and when would you use it over LangChain?

**Answer:**
LlamaIndex (formerly GPT Index) is a framework focused specifically on connecting LLMs with data — indexing, retrieving, and querying structured and unstructured data.

**Core concepts:**
- **Data Connectors** — Ingest data from 100+ sources
- **Indexes** — VectorStoreIndex, SummaryIndex, KnowledgeGraphIndex, etc.
- **Query Engines** — High-level interface for querying over indexed data
- **Retrievers** — Customizable retrieval strategies
- **Data Agents** — Agents that can query multiple data sources intelligently

**LlamaIndex vs LangChain for RAG:**
- LlamaIndex excels at complex RAG scenarios (multi-document, nested indexes, structured data)
- LangChain is more general-purpose and better for full agent orchestration
- Many teams use LlamaIndex for data/retrieval + LangChain/LangGraph for agent orchestration

**Best use cases for LlamaIndex:** Complex document Q&A, multi-document synthesis, structured + unstructured hybrid queries, and production RAG with advanced indexing needs.

---

### Q53. What is LangSmith and how is it used in production?

**Answer:**
LangSmith is LangChain's observability and evaluation platform for LLM applications. It provides:

**Tracing:**
- Full end-to-end trace of every LLM call, tool use, and retrieval step
- Input/output visibility at every node
- Latency, token usage, and cost per step
- Critical for debugging complex agent failures

**Evaluation:**
- Dataset management for creating evaluation test sets
- LLM-as-judge evaluators
- A/B testing between prompt versions
- Regression testing before deploying changes

**Monitoring:**
- Production metrics tracking
- Alerting on anomalies

**How to use:**
```python
import os
os.environ["LANGCHAIN_TRACING_V2"] = "true"
os.environ["LANGCHAIN_API_KEY"] = "<your_key>"
# All LangChain/LangGraph operations are now traced automatically
```

---

## 11. Generative AI (Images, Audio, Multimodal)

---

### Q54. How do diffusion models work for image generation?

**Answer:**
Diffusion models generate images by learning to reverse a noise-adding process:

**Forward process (training):** Gradually add Gaussian noise to a training image over T steps until it becomes pure noise. The model learns to predict the noise at each step.

**Reverse process (inference):** Start from pure random noise. Iteratively denoise using the trained model, guided by a text prompt, until a clean image emerges.

**Key components in modern diffusion models (Stable Diffusion):**
- **Text encoder (CLIP/T5)** — Embeds the text prompt into a latent space
- **U-Net** — The core denoising network; conditions on text embedding at each step
- **VAE (Variational Autoencoder)** — Encodes images into a smaller latent space (Latent Diffusion Models work in this latent space, not pixel space)
- **Scheduler** — Controls the noise schedule (DDPM, DDIM, DPM++ — different speed/quality tradeoffs)

**Popular models:** Stable Diffusion (Stability AI), DALL-E 3 (OpenAI), Midjourney, Flux (Black Forest Labs)

---

### Q55. What are multimodal LLMs? What are their applications?

**Answer:**
Multimodal LLMs can process and generate multiple data modalities — text, images, audio, video — in a unified model.

**Architecture approaches:**
- **Vision-Language Models (VLMs):** A vision encoder (ViT, CLIP) extracts image features; these are projected into the LLM's token space alongside text tokens
- Examples: GPT-4V, Claude 3, Gemini, LLaVA

**Applications:**
- **Visual Q&A** — "What is wrong with this X-ray?"
- **Document understanding** — Parse PDFs, forms, tables with mixed text and images
- **Screenshot analysis** — Debug UI from screenshots; fill forms from documents
- **Medical imaging** — Analyze MRI, CT scans with clinical notes
- **Video understanding** — Summarize videos, answer questions about video content
- **Code + diagram** — Explain architecture diagrams or generate code from wireframes

**Multimodal agent capabilities:** Agents that can "see" the web browser, read PDFs, interpret charts, etc.

---

## 12. LLM Evaluation & Metrics

---

### Q56. How do you evaluate LLM-generated outputs? What metrics and frameworks exist?

**Answer:**

**Automatic metrics:**
- **BLEU** — N-gram overlap between generated and reference text (mainly for translation; doesn't capture semantics)
- **ROUGE** — Recall-oriented; measures overlap of n-grams (used for summarization)
- **BERTScore** — Uses BERT embeddings to compute semantic similarity (better than BLEU/ROUGE)
- **Perplexity** — Measures model confidence; lower = more confident (not always better quality)

**LLM-as-judge:**
- Use a powerful LLM (GPT-4, Claude) to score outputs against criteria (helpfulness, accuracy, safety)
- Can use rubrics: rate 1–5 with specific criteria for each score
- Used in production at scale; cheaper than human evaluation

**Human evaluation:**
- Gold standard for nuanced quality, safety, and user satisfaction
- Expensive; use strategically for final validation and bias discovery
- A/B testing with real users

**Specialized frameworks:**
- **RAGAS** — For RAG-specific metrics (faithfulness, relevancy, precision/recall)
- **TruLens** — End-to-end LLM evaluation including RAG chains
- **Evals (OpenAI)** — Evaluation framework with custom graders
- **LangSmith** — Evaluation + monitoring for LangChain apps

---

### Q57. What is LLM-as-judge? What are its limitations?

**Answer:**
LLM-as-judge uses a powerful LLM (typically GPT-4 or Claude) to automatically evaluate the quality of another LLM's output against defined criteria.

**How it works:**
```
Prompt to judge: "Rate the following response on a scale of 1-5 for factual accuracy.
User question: [question]
Response to evaluate: [response]
Reference answer (optional): [reference]
Provide reasoning and then give a score."
```

**Advantages:**
- Scales cheaply to evaluate thousands of responses
- Can evaluate nuanced criteria that metrics like BLEU can't capture
- Configurable criteria (helpfulness, safety, tone, accuracy)

**Limitations:**
- **Position bias** — Tends to prefer the first option in pairwise comparisons
- **Length bias** — Prefers longer, more verbose answers
- **Self-enhancement bias** — GPT-4 tends to prefer GPT-4's outputs
- **Inconsistency** — Same input can get different scores across runs (add temperature=0 for consistency)
- **Calibration** — Judge scores may not correlate well with human preferences on your specific domain

**Mitigations:** Use multiple judges, reverse order in pairwise comparisons, validate judge calibration on human-labeled subset.

---

## 13. AI Safety, Guardrails & Ethics

---

### Q58. What are guardrails in LLM applications? How do you implement them?

**Answer:**
Guardrails are safety mechanisms that prevent LLMs from generating harmful, biased, off-topic, or policy-violating outputs.

**Types:**
1. **Input guardrails** — Filter malicious or out-of-scope user inputs before sending to the LLM
2. **Output guardrails** — Check and filter LLM outputs before returning to the user
3. **System-level guardrails** — Constitutional rules in the system prompt

**Implementation approaches:**

| Approach | Description | Tools |
|---|---|---|
| **Rule-based** | Regex/keyword filtering for obvious violations | Custom code |
| **Classifier-based** | ML classifier for toxic/unsafe content | OpenAI Moderation API, Perspective API |
| **LLM-based** | Second LLM checks first LLM's output | GPT-4 self-check, Claude |
| **Framework-based** | Declarative guardrail frameworks | NeMo Guardrails (NVIDIA), Guardrails.ai |
| **Prompt-based** | System prompt with explicit constraints | Constitutional AI |

**What to guard against:** Toxicity, PII leakage, hallucinations, off-topic content, prompt injection, jailbreaks, competitor mentions, medical/legal advice.

---

### Q59. What is Constitutional AI?

**Answer:**
Constitutional AI (CAI) is an alignment technique developed by Anthropic to make AI systems helpful, harmless, and honest without relying entirely on human feedback.

**Process:**
1. **Supervised stage:** Generate responses, then use a "constitution" (a set of principles) to critique and revise them
2. **RL stage:** Train a preference model using AI-generated preference data based on the constitution; use it for RLHF

**The "constitution":** A written set of principles like "Choose the response that is least likely to be harmful", "Prefer responses that respect human autonomy", "Avoid responses that could enable violence"

**Advantage over pure RLHF:** More scalable (AI feedback is cheaper than human), more consistent, and principles are explicit and auditable.

---

### Q60. How do you handle PII (Personally Identifiable Information) in LLM applications?

**Answer:**

1. **Data minimization** — Don't send PII to the LLM if not needed for the task

2. **PII detection before ingestion** — Use libraries like `presidio`, `spaCy` NER, or LLM-based detection to identify PII in documents before embedding/storing

3. **Anonymization/pseudonymization** — Replace real names/IDs with pseudonyms before processing; de-anonymize in outputs if needed

4. **Access controls** — Implement role-based access on vector DB; metadata filters per user

5. **No logging of sensitive data** — Ensure observability tools don't log sensitive inputs

6. **On-premise deployment** — For highly sensitive data (medical, legal), use self-hosted open-source LLMs (Llama, Mistral) that keep data within your infrastructure

7. **Data retention policies** — Don't persist conversation logs beyond what's needed

8. **Compliance frameworks** — GDPR, HIPAA, SOC2 requirements must drive these decisions

---

## 14. MLOps & Production Deployment

---

### Q61. How do you deploy an LLM in production? What are the key considerations?

**Answer:**

**Serving options:**
- **API-based (managed):** OpenAI, Anthropic, Google Vertex AI — easy, no infrastructure needed, pay-per-token
- **Self-hosted:** vLLM, TGI (Hugging Face), Ollama, Ray Serve — full control, better cost at scale

**Key considerations:**

| Concern | Description |
|---|---|
| **Latency** | TTFT (time to first token) and total response time; use streaming |
| **Throughput** | Requests per second; use batching in inference servers |
| **Cost** | Token-based pricing; optimize prompt length, use smaller models where appropriate |
| **Scalability** | Auto-scaling based on load; use Kubernetes + HPA |
| **Reliability** | Fallback models, rate limit handling, circuit breakers |
| **Observability** | Log inputs/outputs, latency, costs, errors; use LangSmith/Langfuse |
| **Security** | API key management, rate limiting per user, input validation |
| **Model versioning** | Pin specific model versions to prevent unexpected behavior changes |

**vLLM:** The de facto standard for high-throughput self-hosted LLM serving. Uses paged KV cache (PagedAttention) for efficient memory management and continuous batching for 10–30× throughput improvement over naive serving.

---

### Q62. What is quantization? How does it affect LLM performance?

**Answer:**
Quantization reduces the precision of model weights from floating-point (FP32/FP16) to lower-bit representations (INT8, INT4, INT2).

| Precision | Bits | Size (7B model) | Speedup | Quality |
|---|---|---|---|---|
| FP32 | 32 | ~28 GB | Baseline | Best |
| BF16/FP16 | 16 | ~14 GB | ~2× | Near-identical |
| INT8 | 8 | ~7 GB | ~2-4× | Slight degradation |
| INT4 (GPTQ/AWQ) | 4 | ~3.5 GB | ~4-8× | Moderate degradation |
| INT2 | 2 | ~1.75 GB | ~8-16× | Significant degradation |

**Popular quantization methods:**
- **GPTQ** — Post-training quantization, layer-by-layer; common for 4-bit
- **AWQ (Activation-aware Weight Quantization)** — Identifies and preserves sensitive weights; better quality than GPTQ at same bit-width
- **bitsandbytes** — Runtime quantization for training and inference; used with QLoRA

**Practical use:** For deployment, INT4 (AWQ) gives a great balance of size, speed, and quality. FP16 is used when quality is paramount and GPU memory allows.

---

### Q63. What is LLM inference optimization? Explain KV Cache.

**Answer:**
**KV Cache:**
During autoregressive generation, the attention mechanism computes Key and Value vectors for every previous token at every new token generation step. KV Cache stores these computed K and V vectors in memory so they don't need to be recomputed.

- Without KV cache: O(n²) compute per token
- With KV cache: O(n) compute per token (only compute for the new token)

**Cost:** Memory grows linearly with sequence length and batch size. For very long contexts, KV cache can exhaust GPU memory.

**Other inference optimizations:**
- **Continuous batching** — Dynamically batch requests as they arrive instead of fixed batches (vLLM's innovation)
- **Speculative decoding** — Use a small draft model to generate several tokens, verify with large model — 2–4× speedup
- **Flash Attention** — Efficient attention computation (covered earlier)
- **Tensor parallelism** — Distribute model across multiple GPUs
- **Streaming** — Return tokens as generated; dramatically improves perceived latency

---

## 15. System Design for AI

---

### Q64. How would you design a production RAG system for a large enterprise?

**Answer:**

**Requirements gathering first:** What type of documents? How many? How often updated? Latency requirements? Multitenancy?

**Architecture:**

```
[Documents] → [Ingestion Pipeline] → [Vector DB] + [BM25 Index]
                                            ↓
[User Query] → [Query Transform] → [Hybrid Retriever] → [Reranker]
                                                               ↓
                                          [LLM + Context] → [Answer + Citations]
                                                               ↓
                                          [Guardrails + Eval] → [User]
```

**Key components:**

1. **Ingestion pipeline** (Airflow/Prefect): Document loader → Chunking (semantic) → Embedding → Upsert to vector DB + BM25 index → Metadata storage
2. **Vector database** (Pinecone/Weaviate): With metadata filtering for multi-tenancy
3. **Hybrid retriever**: BM25 + dense search + RRF fusion
4. **Reranker** (Cohere Rerank API): Re-score top-20 → top-5
5. **LLM layer** (GPT-4 or Claude): With strict prompting for faithfulness
6. **Guardrails**: Input validation + output safety check
7. **Observability** (LangSmith/Langfuse): Full traces, eval metrics
8. **Evaluation pipeline**: RAGAS metrics on sampled queries nightly
9. **Caching** (Redis/semantic cache): Cache common query responses to reduce latency and cost
10. **API layer** (FastAPI): Async, rate-limited, authenticated

---

### Q65. How would you design a customer support AI agent?

**Answer:**

**Core components:**

1. **Intent classifier** — Route to specialized sub-agents (billing, technical support, general inquiry)
2. **RAG knowledge base** — Company docs, FAQs, product manuals
3. **CRM integration tool** — Look up customer account, order history, previous tickets
4. **Ticket system tool** — Create/update support tickets
5. **Escalation mechanism** — HITL when agent confidence is low or issue is complex
6. **Memory** — Remember customer context within and across sessions

**Agent flow:**
```
User message → Intent classification → Sub-agent routing
    → Tool: Fetch customer info from CRM
    → Tool: Search knowledge base for relevant answer
    → LLM: Generate empathetic, helpful response
    → Output guardrails: Check for policy violations, PII
    → Response to user (+ optional: Create ticket)
    → If unresolved: Escalate to human agent
```

**Key design decisions:**
- Use a fast, cheap model for intent classification; larger model for generation
- Implement conversation summarization for long sessions
- Set hard limits: no financial commitments, no legal advice
- Fully audit all interactions for compliance

---

## 16. Situational & Scenario-Based Questions

---

### Q66. SCENARIO: Your RAG system retrieves 20 candidate chunks but only 5 fit in the context window. The system frequently gives incomplete answers. How do you fix this?

**Answer:**

This is a classic context window vs. retrieval precision problem. Solutions:

1. **Improve retrieval precision first** — Add a cross-encoder reranker so the top-5 are the truly most relevant, not just the approximately most similar

2. **Smaller, more focused chunks** — If chunks are too large, semantic meaning is diluted. Reduce chunk size to increase density of relevant information per chunk

3. **Query decomposition** — Break the complex query into sub-questions, retrieve and answer each independently, then synthesize

4. **Parent-child chunking** — Retrieve small child chunks for precision, but feed the parent chunk (larger context) to the LLM for completeness

5. **Map-reduce pattern** — Process each chunk independently, then merge results (LangChain's `MapReduceDocumentsChain`)

6. **Upgrade to a model with a larger context window** — If the problem is fundamental, use Claude (200K) or Gemini (1M+) to fit more chunks

7. **Metadata filtering** — Narrow the search space so retrieved chunks are more likely to be relevant

---

### Q67. SCENARIO: Your LLM-powered chatbot is giving confidently wrong answers (hallucinating). Production is affected. What do you do?

**Answer:**

**Immediate triage:**
1. Check if it's a recent model update that changed behavior (pin model version)
2. Check if a specific type of query triggers hallucination
3. Roll back to last known good configuration if possible

**Root cause analysis:**
- Is the knowledge base outdated? → Update vector DB with current information
- Is the retrieval quality poor? → Add reranker, improve chunking
- Is the LLM ignoring context and using parametric knowledge? → Strengthen prompting

**Immediate fixes:**
1. Harden system prompt: "Only answer based on provided context. If the answer is not present, say 'I don't have information about this.'"
2. Reduce temperature to 0 for factual Q&A
3. Add post-generation verification: second LLM call to check if answer is supported by retrieved context

**Long-term fixes:**
1. Implement faithfulness monitoring with RAGAS
2. Add citation requirement to every response
3. Implement CRAG (validate retrieved docs before generation)
4. Fine-tune on domain data with correct answers

---

### Q68. SCENARIO: You need to build an AI system that answers questions from a 10,000-page legal document corpus. The documents contain tables, complex language, and require cross-document reasoning. How would you architect this?

**Answer:**

**Challenges:** Scale (10K pages), tables (not handled well by simple text chunking), cross-document reasoning (multi-hop queries), specialized legal language.

**Architecture:**

1. **Document parsing:** Use specialized parsers:
   - `PyMuPDF`/`pdfplumber` for text extraction
   - `Camelot`/`tabula` for table extraction
   - OCR (Tesseract/AWS Textract) for scanned PDFs

2. **Multi-modal chunking:**
   - Text: Semantic chunking at section/paragraph level
   - Tables: Convert to markdown/JSON with metadata
   - Create separate indexes for text vs. tables

3. **Knowledge graph layer (GraphRAG):**
   - Extract legal entities (parties, dates, clauses, case references)
   - Build relationship graph for multi-hop queries ("What are all cases where X company was held liable for Y under statute Z?")

4. **Hybrid retrieval:** BM25 (legal citations are exact keywords) + dense + knowledge graph traversal

5. **Reranking:** Cross-encoder fine-tuned on legal text

6. **LLM selection:** Use Claude (200K context) for synthesis tasks requiring long context

7. **Citation system:** Every claim must be sourced with document name + page number

8. **Evaluation:** Hire legal experts to create a test set of 200 question-answer pairs; measure accuracy and citation quality

---

### Q69. SCENARIO: Your AI agent is getting stuck in infinite loops in production. How do you diagnose and fix it?

**Answer:**

**Diagnosis:**
1. Pull traces from LangSmith/Langfuse — identify which node/step is cycling
2. Look at the reasoning traces — is the LLM misinterpreting tool results?
3. Check for ambiguous tool responses that cause re-attempts

**Root causes + fixes:**

| Root Cause | Fix |
|---|---|
| Tool returns error the LLM retries indefinitely | Limit retries per tool call (max 3); return unambiguous error |
| LLM can't determine task completion | Explicit completion criteria in system prompt; add "final answer" detection |
| Goal is too vague | Refine task description; add acceptance criteria |
| LLM model limitation | Upgrade to more capable model |
| State corruption | Check state schema for bugs; use typed state in LangGraph |

**Preventive measures:**
1. **Hard step limit** — `max_iterations=25` in all agents
2. **Step monitoring** — Alert when agent exceeds N steps unexpectedly
3. **Timeout** — Kill runs exceeding time threshold
4. **Loop detection** — Track last N (action, observation) pairs; if identical, break loop
5. **LangGraph interrupt conditions** — Add conditional breaks based on state

---

### Q70. SCENARIO: A client asks you to choose between using GPT-4 API vs. deploying an open-source Llama 3 70B model. How do you decide?

**Answer:**

**Key questions to ask:**
- What is the data sensitivity level?
- What is the expected request volume and budget?
- What is the latency requirement?
- Does the use case require customization/fine-tuning?
- What is the team's infrastructure capability?

**Decision framework:**

| Factor | GPT-4 API | Llama 3 70B (self-hosted) |
|---|---|---|
| **Data sensitivity** | Medium (data leaves org) | High (fully on-premise) |
| **Performance** | Higher out-of-the-box | Slightly lower, improvable via fine-tuning |
| **Cost at scale** | Linear with tokens (expensive) | Fixed infrastructure cost (cheap at scale) |
| **Setup time** | Hours | Days to weeks |
| **Maintenance** | None | Full DevOps responsibility |
| **Fine-tuning** | Limited (via OpenAI fine-tune) | Full control |
| **Latency** | Depends on API network | Can optimize (vLLM, hardware) |

**Recommendation framework:**
- Healthcare/legal/finance company with sensitive data → Self-hosted Llama
- Startup needing to ship fast, non-sensitive data → GPT-4 API
- High volume, commodity task (classification, extraction) → Fine-tuned Llama at scale
- Complex reasoning, long context → GPT-4 or Claude API

---

### Q71. SCENARIO: Your embedding model is producing poor retrieval results. Accuracy is low on your domain-specific knowledge base. What steps do you take to improve it?

**Answer:**

**Step-by-step improvement plan:**

1. **Baseline measurement** — Create a test set of (query, relevant_doc) pairs. Measure Recall@10 and MRR@10.

2. **Check embedding model choice** — Generic models (text-embedding-ada-002) struggle with specialized domains. Try domain-specific or more recent models:
   - MTEB benchmark comparison for your language/domain
   - Try `bge-large-en-v1.5`, `e5-large-v2`, Cohere Embed v3

3. **Improve chunking** — Poor chunk quality is often the real issue. Review a sample of retrieved chunks manually.

4. **Add hybrid search** — BM25 for exact terminology retrieval + dense for semantic. Often the single biggest win.

5. **Add reranking** — Even with mediocre embedding retrieval, a strong reranker can save quality.

6. **Fine-tune the embedding model** — Create (query, positive_doc, negative_doc) triplets from your domain data. Fine-tune with contrastive loss. Typical improvement: +10-20% recall.

7. **Query augmentation** — Use HyDE to generate a better query representation before embedding.

8. **Add metadata** — Include document title, section header, and other context in the chunk text before embedding.

---

### Q72. SCENARIO: You're asked to add memory to a customer service chatbot so it remembers users across sessions. How do you design this?

**Answer:**

**Types of memory to persist:**
- User profile (name, preferences, account tier)
- Issue history (what was previously reported and resolved)
- Conversation summaries (key facts from past sessions)
- Explicit user preferences ("I prefer brief answers")

**Architecture:**

```
Session starts:
1. Identify user (auth token)
2. Load user profile from DB
3. Retrieve relevant past memory from vector DB (semantic search over memory)
4. Inject summary of relevant memories into system prompt

During conversation:
5. Detect memory-worthy events ("resolved: billing issue #1234")

Session ends:
6. Summarize conversation
7. Extract entities and facts to remember
8. Store in user's memory store (vector DB + structured DB)
```

**Implementation:**
- **Short-term:** Full message history in context during session
- **Long-term:** LangChain's `ConversationSummaryBufferMemory` + vector store memory
- **Structured data:** Store account facts in PostgreSQL; retrieve on session start
- **Vector memory:** Store conversation summaries; retrieve semantically similar memories

**Privacy considerations:** Inform users that memory is being stored. Provide "forget me" option. Comply with data retention policies.

---

### Q73. SCENARIO: After deploying your LLM app, you notice costs are 10× higher than expected. How do you reduce costs without sacrificing quality?

**Answer:**

**Cost audit first:**
- Break down cost by component: input tokens, output tokens, which model, which endpoint
- Identify which query types are most expensive

**Optimization strategies:**

1. **Prompt optimization** — Reduce prompt length through:
   - Remove redundant instructions
   - Shorter system prompts
   - More concise few-shot examples

2. **Model routing** — Use a cheaper/smaller model for simple queries, expensive model only for complex ones. A classifier or the cheap model itself can make this routing decision.

3. **Caching** — Semantic caching (cache similar queries); exact caching for repeated queries (Redis). Can reduce API calls by 30–60% for FAQ-type systems.

4. **RAG optimization** — Pass fewer chunks; better reranker → smaller context sent to LLM

5. **Output length control** — Set `max_tokens` appropriately; instruct model to be concise

6. **Batch processing** — Use batch API endpoints (usually 50% cheaper) for non-real-time tasks

7. **Quantized self-hosted models** — For very high volume tasks, switch to INT4 Llama on owned hardware

8. **Streaming** — Reduces time and sometimes cost by detecting when to stop generation early

---

### Q74. SCENARIO: You're building a multi-agent system for software development (planner, coder, tester, reviewer). How do you design it?

**Answer:**

**Agent roles:**
- **Planner** — Breaks down feature request into tasks and creates an execution plan
- **Coder** — Writes code for each assigned task
- **Tester** — Writes unit tests, runs them, and reports results
- **Reviewer** — Reviews code for quality, security, and best practices
- **Orchestrator** — Coordinates all agents and manages workflow state

**Workflow (LangGraph):**
```
User Feature Request
    → Planner: Creates task breakdown
    → [For each task]:
        → Coder: Implements task
        → Tester: Writes + runs tests
        → if tests_fail: Coder fixes (loop, max 3 attempts)
        → Reviewer: Reviews code
        → if review_issues: Coder refines
    → Orchestrator: Merge + final validation
    → Human approval gate (HITL)
    → Deploy
```

**Key design decisions:**
- Use specialized system prompts for each agent role
- Shared state holds: task list, code files, test results, review comments
- Checkpointing after each task completion for recovery
- Time/iteration limits on coder-tester loops to prevent infinite cycles
- Human-in-the-loop before final deployment

---

## 17. Behavioral & HR Questions

---

### Q75. Tell me about a challenging AI project you built. What was the hardest part?

**Answer (Framework to use - STAR: Situation, Task, Action, Result):**

Structure your answer as:

- **Situation:** Brief context about the project (company, goal, scale)
- **Task:** Your specific role and responsibility
- **Action:** What you did, technical decisions made, challenges overcome
- **Result:** Measurable outcome (latency improved by X%, accuracy improved by Y%, saved $Z)

**Example topics to discuss:**
- Building a production RAG system and improving retrieval quality from 60% to 90% relevance
- Debugging a hallucinating chatbot and implementing faithfulness guardrails
- Optimizing a slow agent to meet sub-3-second latency requirements
- Fine-tuning a model that initially suffered from catastrophic forgetting

---

### Q76. How do you stay up to date with the rapidly evolving AI/LLM space?

**Answer:**
A strong answer includes multiple sources and demonstrates a systematic approach:

**Research & Papers:**
- arXiv (cs.CL, cs.AI sections) — daily reading of important papers
- Hugging Face Daily Papers — curated important research
- Papers With Code — implementations alongside papers

**Engineering blogs:**
- LangChain, Anthropic, OpenAI, Google DeepMind engineering blogs
- Chip Huyen's blog, Sebastian Ruder's NLP newsletter
- Towards Data Science, The Gradient

**Hands-on practice:**
- Personal projects using new models/frameworks
- Running local experiments with Ollama, LM Studio
- Reproducing paper results in notebooks

**Community:**
- Twitter/X (follow key researchers and engineers)
- Discord servers (Hugging Face, LangChain)
- AI Engineer Summit, NeurIPS, ICLR conference materials

---

### Q77. How would you explain RAG to a non-technical stakeholder?

**Answer:**

"Imagine you hired a brilliant consultant, but their knowledge is frozen from the day they graduated. Every time you ask them something, they can only use what they knew back then.

RAG is like giving that consultant a library card and a research assistant. Before they answer your question, they first search the most relevant documents in your company's library, read the relevant pages, and then use that fresh, specific information to give you an accurate answer.

This means our AI assistant can answer questions about your latest product releases, recent policy changes, or internal data — not just things it learned in its training months ago. And it can actually show you which documents it used to come up with the answer."

---

### Q78. What would you do if you strongly disagreed with a technical decision your team lead made about the AI system architecture?

**Answer:**

Strong answers demonstrate both technical conviction and professional maturity:

1. **Seek to understand first** — Ask clarifying questions about the reasoning; perhaps there are constraints you're not aware of
2. **Present your case with data** — Document your concerns with specific technical evidence, prototype the alternative if feasible
3. **Frame around outcomes** — "I'm concerned this approach may cause X problem for these reasons..." not "your approach is wrong"
4. **Respect the decision-making process** — Voice disagreement clearly once through appropriate channels, but commit to the team's decision once made
5. **Document your concerns** — So they can be revisited if the predicted issues arise
6. **Escalate appropriately** — Only escalate if the decision poses significant risk (security, reliability, major cost) and reasoning hasn't been heard

---

### Q79. How do you ensure the AI applications you build are ethical and responsible?

**Answer:**

1. **Bias auditing** — Test the system on diverse demographic groups; use evaluation datasets like WinoBias, HolisticBias
2. **Transparency** — Make it clear to users they're interacting with AI; show citations and sources
3. **Guardrails** — Implement safety layers to prevent harmful outputs
4. **Privacy by design** — Minimize PII collection; anonymize where possible; comply with GDPR/HIPAA
5. **Human oversight** — Maintain HITL for high-stakes decisions; don't fully automate consequential actions
6. **Red-teaming** — Actively try to break the system before deployment; document findings
7. **Monitoring** — Continuously audit production outputs for bias drift or policy violations
8. **Stakeholder involvement** — Include diverse perspectives (including end users) in design
9. **Incident response plan** — Have a plan for when the AI causes harm; ability to quickly disable

---

## 18. Advanced & Research-Level Questions

---

### Q80. What is attention sink and why does it occur in long-context LLMs?

**Answer:**
Attention sink is a phenomenon where LLMs disproportionately attend to the first few tokens of the input (especially the first token) regardless of their semantic relevance, even in very long contexts.

**Why it happens:** The first token receives very high attention scores during pre-training because it's always present and serves as a "sink" for excess attention that needs to sum to 1 via softmax. The model learns to dump attention to it when no other tokens are highly relevant.

**Implications:**
- Important information placed in the middle of very long contexts may be under-attended (the "lost in the middle" problem)
- Performance on very long-context tasks can degrade significantly

**Mitigations:**
- **StreamingLLM** — Keeps the attention sink tokens (first few) + a sliding window of recent tokens; enables infinite-length text generation without performance degradation
- **Instruction placement** — Put critical instructions at the beginning AND end of the context
- **Position interpolation** — Techniques to extend context gracefully

---

### Q81. What are Mixture of Experts (MoE) models? How do they work?

**Answer:**
Mixture of Experts is an architecture where instead of one monolithic feed-forward layer, there are N "expert" sub-networks and a learned router that selects K experts (top-K routing, typically K=2) for each token.

**How it works:**
- Input token → Router (gating network) → Selects top-2 experts out of N
- Token is processed by selected experts in parallel
- Outputs are combined (weighted sum based on router probabilities)

**Benefits:**
- **Scale without proportional compute cost** — Mixtral 8×7B has 56B total parameters but only activates ~13B per token (same compute as a 13B dense model at inference)
- **Specialization** — Different experts can specialize in different domains/skills

**Examples:** Mixtral 8×7B, GPT-4 (likely MoE), Gemini 1.5, DeepSeek MoE

**Challenges:**
- Load balancing — All experts should be utilized; auxiliary loss prevents routing collapse
- Communication overhead — In distributed training, expert parallelism introduces communication costs
- Memory — Must load all expert weights even though only a few are activated per token

---

### Q82. What is RLHF vs DPO vs GRPO? Compare alignment methods.

**Answer:**

**RLHF (Reinforcement Learning from Human Feedback):**
- Trains a separate reward model on preference data
- Uses PPO (RL) to optimize the language model against the reward model
- Complex pipeline; reward hacking possible; training instability
- Requires significant compute for RL training

**DPO (Direct Preference Optimization):**
- Mathematical reformulation that eliminates the reward model entirely
- Trains directly on preference pairs (winner response, loser response)
- More stable and simpler than RLHF
- Equivalent to RLHF under certain assumptions
- Used widely for alignment fine-tuning

**GRPO (Group Relative Policy Optimization):**
- Used by DeepSeek-R1 for reasoning alignment
- Samples multiple responses per prompt, scores them, uses relative rewards within the group
- No critic model needed; uses group statistics as baseline
- Particularly effective for teaching mathematical reasoning

**Modern trend:** RLHF's PPO is being replaced by DPO and GRPO in most fine-tuning pipelines due to simplicity and stability. Constitutional AI + DPO is a common production recipe.

---

### Q83. What is Speculative Decoding? How does it speed up inference?

**Answer:**
Speculative Decoding uses a small, fast "draft" model to speculatively generate several tokens ahead, then verifies them with the large "target" model in parallel.

**Process:**
1. Small draft model (e.g., Llama 7B) generates K tokens speculatively (e.g., K=5)
2. Large target model (e.g., Llama 70B) verifies all K tokens in a single forward pass (parallel, not sequential)
3. Accept tokens where the target model agrees; reject and resample the first disagreement
4. Net result: 1+ tokens accepted per large model forward pass (1 is guaranteed, often 3–4 accepted)

**Speed improvement:** 2–4× latency reduction without any change to output quality (mathematically equivalent to sampling from the target model).

**Why it works:** The large model runs efficiently in parallel over multiple tokens. The bottleneck in autoregressive generation is the sequential nature, not per-step compute.

**Practical use:** Used in production by Anthropic, Google, and in libraries like vLLM.

---

### Q84. What is Retrieval-Augmented Fine-Tuning (RAFT)?

**Answer:**
RAFT (Retrieval-Augmented Fine-Tuning) is a technique that combines fine-tuning with RAG-style training to teach the model how to answer questions in the presence of retrieved documents — including irrelevant "distractor" documents.

**Standard fine-tuning problem:** When a model is fine-tuned on domain-specific QA data, it learns to answer questions from memory. But in production with RAG, it receives retrieved context (which may include irrelevant chunks). The model doesn't know how to selectively use retrieved context.

**RAFT solution:**
- Fine-tune on (question, context with distractors, answer with chain-of-thought citing relevant context)
- The model learns to:
  1. Identify which retrieved documents are relevant vs. distractors
  2. Generate answers grounded in the relevant context
  3. Produce chain-of-thought reasoning citing specific source passages

**Result:** Models fine-tuned with RAFT significantly outperform standard fine-tuning and standard RAG on domain-specific tasks because they learn to be selective about retrieved context.

---

### Q85. What are reasoning models (o1, DeepSeek-R1, Claude's extended thinking)? How are they different?

**Answer:**
Reasoning models are LLMs trained to generate extended internal reasoning chains (often hidden "thinking" tokens) before producing a final answer, dramatically improving performance on complex reasoning tasks.

**How they work:**
- The model generates a long internal scratchpad (chain-of-thought) before the final answer
- This thinking is often hidden from users but visible in extended thinking mode
- Trained using RL to reinforce reasoning patterns that lead to correct answers
- DeepSeek-R1 uses GRPO to train this reasoning capability

**Performance:** Reasoning models (o3, DeepSeek-R1) dramatically outperform standard models on:
- Mathematical competition problems (AIME, AMC)
- Competitive programming (Codeforces)
- Scientific reasoning (GPQA, MMLU)

**When to use reasoning models:**
- Complex multi-step math or logic problems
- Difficult coding challenges
- Deep analysis requiring careful step-by-step reasoning

**When NOT to use:**
- Simple factual Q&A (overkill, expensive, slow)
- Latency-sensitive applications (extended thinking takes longer)
- Creative writing or conversational tasks

---

### Q86. What is the "lost in the middle" problem in LLMs?

**Answer:**
Research has shown that LLMs perform significantly better at using information located at the beginning and end of the context window compared to information in the middle — even when the context fits within the window.

**Why it happens:**
- Positional bias in attention: tokens far from the query token receive less attention
- Training data characteristics: most training documents have key information at the start
- Attention sink: excessive attention to first tokens

**Implications for RAG:**
- Don't put the most critical context in the middle of a long list of retrieved chunks
- Put the most relevant chunk first AND last (or just first)
- Consider chunk reordering strategies

**Mitigations:**
- "Lost in the middle" aware reranking: place best chunks at extremes
- Reduce number of chunks to decrease total context length
- Use models trained specifically for long-context retrieval

---

### Q87. What is Agentic Chunking / Late Chunking?

**Answer:**

**Late Chunking:**
A technique where the entire document is first processed by the embedding model to generate contextualized embeddings for all tokens, and THEN chunked. This means each chunk's embedding contains context from the entire document.

**Traditional approach:** Chunk first → Embed each chunk independently → Each embedding loses global document context

**Late chunking advantage:** Chunk embeddings are more semantically rich because the full context influences them. Particularly useful for documents where local chunks have ambiguous meaning without global context (e.g., pronouns, references to previous sections).

**Agentic/Semantic Chunking:**
Uses an LLM to identify natural semantic boundaries in the document rather than using fixed-size or rule-based splitting.

- An LLM reads the document and identifies where topics/concepts change
- Chunks follow natural document structure (idea completeness)
- Results in more coherent chunks that retrieve better
- More expensive (requires LLM call during indexing)

---

### Q88. What is the difference between Tool Calling vs Function Calling vs MCP?

**Answer:**

**Function Calling (OpenAI original term):**
- Specific to OpenAI API; allows the LLM to output structured JSON indicating which function to call with what arguments
- The developer defines functions, the model outputs structured call; developer executes the function
- Now more broadly called "tool calling" or "tool use"

**Tool Calling (modern standard term):**
- The broader concept; now standard across providers (Anthropic tool use, Google Vertex tools)
- LLM outputs a structured call → developer executes → returns result to LLM
- Tools are defined with name, description, and input schema (JSON Schema)

**MCP (Model Context Protocol):**
- A standardization layer above tool calling
- Defines a standard protocol for how tool servers are built and discovered
- Enables one tool server to work with any MCP-compatible client
- Handles server lifecycle, resource management, and multi-capability tools

**Summary:** Function calling = mechanism. Tool calling = same thing, broader terminology. MCP = standardized protocol for building and connecting tools at an ecosystem level.

---

### Q89. How would you implement streaming responses in an LLM application?

**Answer:**
Streaming returns tokens to the user as they are generated rather than waiting for the complete response, dramatically improving perceived latency.

**Why it matters:** For a response that takes 10 seconds to generate, streaming means the user sees the first tokens in <0.5 seconds (TTFT). Without streaming, they wait 10 seconds for any output.

**Implementation (Python/FastAPI):**

```python
# Server-side streaming with FastAPI
from fastapi import FastAPI
from fastapi.responses import StreamingResponse
import anthropic

app = FastAPI()
client = anthropic.Anthropic()

@app.get("/stream")
async def stream_response(prompt: str):
    async def generator():
        with client.messages.stream(
            model="claude-sonnet-4-6",
            max_tokens=1024,
            messages=[{"role": "user", "content": prompt}],
        ) as stream:
            for text in stream.text_stream:
                yield f"data: {text}\n\n"
    return StreamingResponse(generator(), media_type="text/event-stream")
```

**Client-side:** Use `EventSource` (SSE) or WebSocket to receive and display tokens incrementally.

**LangChain streaming:**
```python
for chunk in chain.stream({"input": "Hello"}):
    print(chunk, end="", flush=True)
```

---

### Q90. What is Semantic Caching and how does it reduce LLM costs?

**Answer:**
Semantic caching caches LLM responses not by exact string match but by semantic similarity — so if a similar (but not identical) question was asked before, the cached answer is returned.

**How it works:**
1. User submits query → Embed the query
2. Search semantic cache (vector DB or Redis with vector search) for similar previous queries
3. If similarity > threshold (e.g., 0.95): Return cached response immediately (no LLM call)
4. If cache miss: Call LLM, store (query embedding, response) in cache

**Cost impact:**
- FAQ-style applications can see 40–70% cache hit rates
- Eliminates token costs for repeated/similar queries
- Near-zero latency for cache hits

**Implementations:** GPTCache, LangChain's `CacheBackedEmbeddings`, Redis with vector search, custom vector DB layer

**Considerations:**
- Set appropriate similarity threshold (too low = wrong answers returned; too high = few cache hits)
- TTL (time-to-live) for knowledge that becomes stale
- Don't cache responses with user-specific context (PII, account info)

---

### Q91. How do you implement citation and source attribution in RAG?

**Answer:**
Citations ground the LLM's response and allow users to verify claims:

**Prompt-level approach:**
```
System: "Answer the user's question based ONLY on the provided documents. 
For every factual claim, cite the source using [Doc N] format at the end of the sentence."

Context:
[Doc 1]: {chunk_1}
[Doc 2]: {chunk_2}
[Doc 3]: {chunk_3}

User: {question}
```

**Structured output approach:**
- Ask the LLM to output JSON: `{"answer": "...", "citations": [{"doc_id": 1, "quote": "..."}, ...]}`
- Parse structured output programmatically
- Display citations as footnotes/links in UI

**Verification step:**
- After generation, use a second LLM call to verify each claim is supported by the cited chunk
- Removes uncited claims or marks them as unverified

**LlamaIndex citation engine:**
```python
from llama_index.core.query_engine import CitationQueryEngine
query_engine = CitationQueryEngine.from_args(index, citation_chunk_size=512)
response = query_engine.query("What is the refund policy?")
# response.source_nodes contains attribution
```

---

### Q92. What is Model Quantization-aware Training (QAT) vs Post-Training Quantization (PTQ)?

**Answer:**

**Post-Training Quantization (PTQ):**
- Quantize the model after training is complete
- Fast and easy — no retraining needed
- Some accuracy loss, especially at 4-bit
- Methods: GPTQ, AWQ, bitsandbytes
- Best for inference optimization when you can't retrain

**Quantization-Aware Training (QAT):**
- Simulate quantization during training (fake quantization)
- The model learns to be robust to quantization noise
- Higher accuracy at same bit-width compared to PTQ
- Much more expensive (requires full training run)
- Used when highest possible accuracy at low precision is needed

**For LLMs in practice:**
- PTQ (AWQ at 4-bit) is the standard for most deployments — excellent quality/speed tradeoff
- QAT is used for edge device deployment where extreme compression is needed
- INT8 PTQ has negligible quality loss; INT4 PTQ has small but measurable degradation

---

### Q93. What is Structured Output / JSON mode in LLMs and how do you implement it reliably?

**Answer:**
Structured output forces the LLM to generate responses that conform to a specified JSON schema, enabling programmatic processing of LLM outputs.

**Why it's important:**
- LLM outputs need to integrate with downstream systems (databases, APIs, UIs)
- Free-form text is unpredictable; JSON schema ensures parseable structure
- Reduces post-processing complexity

**Methods:**

1. **Prompt-only (unreliable):** "Respond only in JSON format with keys: name, age, email"
   - Often fails for complex schemas; model may add prose around JSON

2. **Provider JSON mode:** `response_format={"type": "json_object"}` (OpenAI) — forces valid JSON but doesn't enforce schema

3. **Constrained decoding (best):** Libraries like Outlines, Guidance constrain token sampling to only allow tokens that form valid JSON matching the schema. 100% schema compliance.

4. **Instructor library:** Wraps OpenAI/Anthropic/etc.; uses function calling to enforce Pydantic schemas with automatic retries

```python
import instructor
from pydantic import BaseModel

client = instructor.from_anthropic(anthropic.Anthropic())

class User(BaseModel):
    name: str
    age: int

user = client.messages.create(
    model="claude-sonnet-4-6",
    messages=[{"role": "user", "content": "John is 28 years old"}],
    response_model=User,
)
# user.name == "John", user.age == 28
```

---

### Q94. What are the common failure modes of RAG systems?

**Answer:**

| Failure Mode | Description | Fix |
|---|---|---|
| **Missing context** | Relevant document not retrieved | Improve chunking, add hybrid search, increase top-k |
| **Irrelevant retrieval** | Retrieved chunks unrelated to query | Better embedding model, add reranker, improve metadata filtering |
| **Context ignored** | LLM ignores retrieved context, uses parametric knowledge | Stronger prompting, reduce temperature, CRAG validation |
| **Outdated knowledge base** | Vector DB not updated with new documents | Automated ingestion pipeline with change detection |
| **Chunking errors** | Chunks cut mid-sentence or mid-concept | Better chunking strategy, overlap, semantic chunking |
| **Embedding drift** | New documents added with different embedding model version | Consistent embedding model; re-embed when upgrading |
| **Table/figure blindness** | Structured content not extracted properly | Specialized parsers, multimodal LLMs |
| **Query-document vocabulary mismatch** | User uses different terms than documents | Synonyms, query expansion, HyDE |
| **Long document sections lost** | Important content in long documents missed | Parent-child chunking, summary indices |

---

### Q95. How do you handle multi-lingual support in LLM applications?

**Answer:**

1. **Model selection** — Choose multilingual base models: Llama 3 (multilingual), Mistral, mT5, mBERT. Verify model's language coverage for your target languages.

2. **Multilingual embeddings** — Use multilingual embedding models for cross-lingual RAG: `multilingual-e5-large`, `paraphrase-multilingual-mpnet-base-v2`. Ensures documents in French can be retrieved by queries in Spanish.

3. **Language detection** — Detect input language and route to language-specific handling if needed.

4. **System prompt localization** — Write system prompts in the user's language for better adherence.

5. **Zero-shot cross-lingual transfer** — Many models trained primarily on English perform reasonably on other languages, especially high-resource languages (French, German, Spanish, Chinese, Japanese).

6. **If quality is insufficient** — Fine-tune on target language data. Create few-shot examples in target language. Add chain-of-thought in target language.

7. **Evaluation** — Evaluate on language-specific test sets. Quality often differs significantly between languages even for the same model.

---

### Q96. What is Graph RAG and when would you use it over standard RAG?

**Answer:**
Graph RAG (popularized by Microsoft Research) builds a knowledge graph from the document corpus rather than (or in addition to) a flat vector index.

**How it works:**
1. Extract entities and relationships from documents using LLM
2. Build a knowledge graph: (Entity A) --[relationship]--> (Entity B)
3. Create community summaries at multiple granularity levels (hierarchical clustering)
4. At query time: traverse the graph and retrieve relevant entity neighborhoods + community summaries

**Standard RAG vs Graph RAG:**

| | Standard RAG | Graph RAG |
|---|---|---|
| Best for | Specific factual questions | Questions requiring synthesis across many documents |
| Retrieval | Vector similarity | Graph traversal + vector |
| Multi-hop reasoning | Poor (requires multiple retrieval steps) | Native |
| Relationships | Lost in chunks | Explicit |
| Cost | Lower | Higher (graph construction is expensive) |

**Use Graph RAG when:**
- "What are the common themes across all these customer complaint reports?"
- "How are these 50 research papers related?"
- Multi-hop: "Find all drugs that interact with X, then find their contraindications with Y"
- Social network analysis, code dependency graphs, knowledge management

---

### Q97. What is RAPTOR (Recursive Abstractive Processing for Tree-Organized Retrieval)?

**Answer:**
RAPTOR is an advanced indexing technique that creates a hierarchical tree of summaries over the document corpus, enabling retrieval at different levels of abstraction.

**How it works:**
1. Chunk documents at the leaf level
2. Cluster similar chunks using UMAP dimensionality reduction + Gaussian Mixture Models
3. Generate LLM summary for each cluster
4. Repeat: cluster summaries → summarize clusters of summaries
5. Build a tree: leaves = original chunks, nodes = progressively higher-level summaries

**Retrieval:** Query against all levels simultaneously (collapsed tree retrieval) or navigate top-down

**When to use RAPTOR:**
- Questions requiring high-level synthesis: "What is the overall strategy described in these documents?"
- Questions spanning multiple documents
- When standard chunk-level retrieval misses the forest for the trees

**Standard RAG is sufficient for:** Specific factual lookups, "What does page 5 say about X?"

---

### Q98. What is Constitutional AI and RLAIF (RL from AI Feedback)?

**Answer:**

**Constitutional AI (CAI) — Anthropic:**
A multi-stage alignment technique:
1. **SL-CAI:** Use a set of written principles (the "constitution") to critique and revise harmful model outputs through automated AI feedback
2. **RL-CAI:** Train a preference model using AI-generated comparisons (based on the constitution), then use RL to align the model

**RLAIF (Reinforcement Learning from AI Feedback):**
A generalization: instead of human raters creating preference pairs (RLHF), use an AI system (usually a more capable LLM) to generate preference labels.

**Advantages over pure RLHF:**
- **Scalability** — AI feedback is orders of magnitude cheaper and faster
- **Consistency** — AI applies principles more consistently than human annotators
- **Transparency** — Written principles can be audited and updated
- **Reduced human exposure** — Human annotators aren't exposed to harmful content

**Limitation:** AI feedback models can carry the biases of the AI system used for feedback. Hybrid human+AI feedback is common in practice.

---

### Q99. Explain the differences between Pinecone, Weaviate, Chroma, Qdrant, and pgvector. When would you choose each?

**Answer:**

| Database | Type | Best For |
|---|---|---|
| **Pinecone** | Managed cloud | Production at scale; no ops overhead; high SLA requirements |
| **Weaviate** | Open-source/managed | Hybrid search native; rich metadata; GraphQL API; multi-modal |
| **Chroma** | Open-source | Local development; small scale; developer-friendly; embeddings included |
| **Qdrant** | Open-source/managed | High-performance filtering; Rust-based; great for complex metadata queries |
| **FAISS** | Library (in-memory) | Offline processing; research; when you manage your own index; no persistence |
| **pgvector** | Postgres extension | Already on Postgres; want to avoid new infrastructure; smaller scale |
| **Milvus** | Open-source | Enterprise scale; Kubernetes-native; complex deployments |

**Decision guide:**
- Startup/prototype → Chroma locally, Pinecone for production
- Heavy filtering requirements → Qdrant
- Already on Postgres, < 10M vectors → pgvector
- Need hybrid search out of the box → Weaviate
- Massive enterprise scale (1B+ vectors) → Milvus or Pinecone

---

### Q100. What is the future of AI Engineering? What skills should an AI Engineer develop?

**Answer:**

**Emerging trends:**
1. **Agentic AI everywhere** — Most applications will have autonomous agents replacing manual workflows
2. **Multimodal as standard** — Text + image + audio + video as standard input/output
3. **Smaller, specialized models** — Edge deployment with efficient models (Phi, Gemma, Llama 3.2)
4. **AI + traditional software merging** — AI engineers need strong SWE skills; SWEs need AI knowledge
5. **Reasoning models** — Chain-of-thought and extended thinking becoming mainstream
6. **MCP ecosystem** — Standardized tool integration across the industry
7. **Evaluation as a discipline** — Robust evals becoming as important as the model itself

**Skills to develop:**
- **Distributed systems + MLOps** — Scaling AI systems in production
- **Evaluation design** — Building test sets, eval frameworks, and monitoring
- **Agent patterns + LangGraph** — Complex agentic workflow design
- **System design** — Architecting robust, scalable AI pipelines
- **Security** — Prompt injection, jailbreak defense, AI-specific threats
- **Domain expertise** — AI + Medicine, AI + Finance, AI + Code are more valuable than generic AI
- **Research literacy** — Ability to read and implement papers quickly

---

## Appendix: Quick Reference Cheat Sheet

### Key Terms at a Glance

| Term | One-line Definition |
|---|---|
| **LLM** | Large language model trained on text to understand and generate language |
| **Transformer** | Neural architecture using self-attention; backbone of all modern LLMs |
| **RAG** | Retrieve relevant documents at runtime; inject into LLM context |
| **Embedding** | Dense vector representation of text capturing semantic meaning |
| **Fine-tuning** | Further training a pre-trained model on new task-specific data |
| **LoRA** | Efficient fine-tuning by adding trainable low-rank matrices to frozen weights |
| **RLHF** | Align LLM using human preference rankings + reinforcement learning |
| **DPO** | Simpler RLHF alternative; optimize directly on preference pairs |
| **Agent** | LLM + tools + memory + loop = autonomous task execution system |
| **ReAct** | Thought → Action → Observation loop for agent reasoning |
| **Chain-of-Thought** | Prompt LLM to reason step by step before answering |
| **Hallucination** | Confident but factually incorrect LLM output |
| **Chunking** | Splitting documents into pieces for embedding and retrieval |
| **Reranker** | Cross-encoder that rescores retrieved candidates for better precision |
| **KV Cache** | Cache computed Key/Value attention states; speeds up generation |
| **Quantization** | Reduce model weight precision (e.g., FP16 → INT4) to save memory/speed |
| **MoE** | Mixture of Experts; sparse model architecture with expert routing |
| **HITL** | Human-in-the-loop; pause agent for human approval at critical steps |
| **MCP** | Model Context Protocol; standard for connecting LLMs to tools |
| **vLLM** | High-throughput LLM serving library with PagedAttention |
| **Flash Attention** | IO-aware attention algorithm; faster + less memory than standard attention |
| **Speculative Decoding** | Draft model generates candidates; large model verifies in parallel |

---

*Last Updated: 2026 | Covers AI Engineer, LLM Engineer, AI Agent Developer, Generative AI Developer roles*

*Total Questions: 100 primary Q&As with extensive sub-questions and scenario coverage*
