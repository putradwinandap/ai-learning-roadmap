# Level 09 topics

Full lesson files are planned. Until then, your AI mentor teaches these topics in order (`/lesson`), using the resources below.

| # | Topic | Key ideas |
|---|---|---|
| 01 | LLM fundamentals | Tokens, context windows, temperature and sampling, hallucination, model families and sizes |
| 02 | Working with LLM APIs | Messages, system prompts, streaming, structured output (JSON schema), rate limits, retries, timeouts |
| 03 | Prompt engineering | Clear instructions, examples (few-shot), decomposition, prompt templates and versioning |
| 04 | Embeddings & vector search | Embeddings, similarity, vector databases (pgvector, ...), hybrid search (BM25 + vectors) |
| 05 | RAG | Ingestion, chunking strategies, metadata filters, reranking, citations, freshness |
| 06 | Tool use | Function/tool calling, schemas, validating tool inputs, side-effect confirmation |
| 07 | Agents | Agent loops, planning, memory, multi-step workflows vs. agents, MCP, when *not* to use an agent |
| 08 | Evaluation | Golden datasets, task-specific metrics, LLM-as-judge and its biases, human review, regression tests in CI |
| 09 | Safety & security | Prompt injection (direct and indirect), data exfiltration, PII, OWASP Top 10 for LLM Applications, output filtering |
| 10 | Cost & latency | Token accounting, prompt caching, model routing, batching, streaming UX |
| 11 | LLMOps | Tracing, feedback collection, prompt/model versioning, A/B testing, monitoring drift |
| 12 | Fine-tuning & alternatives | When to fine-tune vs. RAG vs. prompting, small models, distillation (overview) |

## Resources

- Provider docs (pick yours): [Anthropic](https://docs.anthropic.com/), [OpenAI](https://platform.openai.com/docs), [Google Gemini](https://ai.google.dev/gemini-api/docs), [Ollama](https://ollama.com/)
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/)
- [Anthropic: Building effective agents](https://www.anthropic.com/research/building-effective-agents)
- [Model Context Protocol](https://modelcontextprotocol.io/)
- [Hamel Husain: Your AI product needs evals](https://hamel.dev/blog/posts/evals/)
- [pgvector](https://github.com/pgvector/pgvector)
- *AI Engineering*, by Chip Huyen (book)
