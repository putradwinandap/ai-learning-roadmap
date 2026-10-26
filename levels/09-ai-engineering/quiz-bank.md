# Level 09 quiz bank

See [ai/quiz-protocol.md](../../ai/quiz-protocol.md).

## 1. LLM fundamentals
- What is a token? Why do context windows matter for cost and quality?
- What does temperature change?
- Why do LLMs hallucinate? Two ways to reduce it.

## 2. APIs & prompting
- System prompt vs user message.
- Why use structured output / JSON schema instead of parsing free text?
- How should you handle rate-limit errors from a provider?

## 3. Embeddings & RAG
- What is an embedding? What does cosine similarity measure?
- Trade-offs of small vs large chunks.
- Why combine keyword (BM25) and vector search?
- What is reranking?

## 4. Tools & agents
- How does tool calling work, step by step?
- Workflow vs agent: when is an agent justified?
- Why must side-effecting tools require confirmation?
- What is MCP?

## 5. Evaluation
- Why can't you rely on manual spot checks?
- What is LLM-as-judge? Name two of its biases and how to mitigate them.
- What goes into a good golden dataset?
- Faithfulness vs answer relevance.

## 6. Safety
- Direct vs indirect prompt injection, with an example of each.
- *Apply:* the assistant reads event descriptions written by any user. What could go wrong, and how do you defend?
- How do you prevent cross-tenant data leakage in RAG?

## 7. Cost, latency & ops
- Name three ways to reduce cost without hurting quality much.
- What should a trace of one assistant request contain?
- Fine-tuning vs RAG vs prompting: when does each fit?
