# 🧠 LLM Knowledge Base System

A local, extensible system for building **LLM-native personal knowledge bases** from research materials.

This project transforms raw documents (papers, articles, repos, etc.) into a **structured, queryable knowledge system** using markdown, YAML schemas, and a lightweight CLI.

---

## 🚀 Overview

This system is designed around a simple idea:

> **Use LLMs to compile, structure, and continuously improve knowledge—not just retrieve it.**

Instead of traditional RAG pipelines, this approach:

* Builds a **persistent wiki**
* Maintains a **knowledge graph**
* Enables **iterative reasoning and exploration**

---

## 🏗️ Architecture

The system consists of four layers:

### 1. Raw Data (`/raw`)

Immutable source materials:

* Papers
* Articles
* Repositories
* Images

---

### 2. Index Layer (`/index`)

Structured metadata (YAML):

* Documents
* Concepts
* Knowledge graph (`graph.json`)

👉 This acts as the **source of truth for the LLM**

---

### 3. Wiki Layer (`/wiki`)

Generated markdown knowledge base:

* Concept pages
* Backlinks
* Structured summaries

👉 Designed for viewing in tools like **Obsidian**

---

### 4. Outputs (`/outputs`)

Generated artifacts:

* Reports
* Slides
* Experiments

👉 Outputs can be fed back into the system

---

## 📁 Folder Structure

```
kb/
├── raw/
├── index/
│   ├── documents/
│   ├── concepts/
│   └── graph.json
├── wiki/
├── outputs/
├── tools/
│   └── kb.py
├── db/
└── config.yaml
```

---

## 📄 Schemas

### Document Schema (`index/documents/*.yaml`)

```yaml
id: doc_001
title: Attention Is All You Need
type: paper
source: https://...
tags: [transformer, attention]
summary_short: Short summary
summary_long: |
  Detailed explanation...
key_points:
  - Key idea 1
  - Key idea 2
citations:
  - Vaswani et al. 2017
related:
  - doc_002
```

---

### Concept Schema (`index/concepts/*.yaml`)

```yaml
id: concept_transformer
name: Transformer
description: Neural architecture based on attention
related_concepts:
  - Attention
  - Self-Attention
source_docs:
  - doc_001
```

---

### Graph Schema (`index/graph.json`)

```json
{
  "nodes": [],
  "edges": []
}
```

---

## ⚙️ CLI Usage

All commands are run via:

```bash
python kb/tools/kb.py <command>
```

---

### 🔍 Search

```bash
python kb/tools/kb.py search --query "attention"
```

Searches across indexed documents.

---

### 🔗 Build Knowledge Graph

```bash
python kb/tools/kb.py build_graph
```

Generates relationships between concepts.

---

### 📚 Build Wiki

```bash
python kb/tools/kb.py build_wiki
```

Creates markdown files from concept schemas.

---

### 🧹 Lint

```bash
python kb/tools/kb.py lint
```

Checks for:

* Duplicate concepts
* Structural issues

---

## 🔄 Typical Workflow

1. Add raw data → `/raw`
2. Create document metadata → `/index/documents`
3. Define concepts → `/index/concepts`
4. Build graph → `build_graph`
5. Generate wiki → `build_wiki`
6. Explore + query → iterate

---

## 🧠 Design Principles

* **Separation of concerns**

  * Raw data ≠ structured knowledge ≠ generated content

* **LLM as compiler, not source of truth**

  * YAML schemas ground the system

* **Incremental improvement**

  * Every query and output can enhance the knowledge base

* **Graph-first thinking**

  * Concepts and relationships matter more than documents

---

## 🔮 Roadmap

### Short-term

* Backlink auto-generation
* Semantic search (FAISS)
* LLM integration for Q&A

### Mid-term

* Multi-agent pipeline (ingest / compile / critique)
* Knowledge graph visualization
* Automated concept extraction

### Long-term

* Synthetic data generation
* Fine-tuned local models
* Fully autonomous research assistant

---

## ⚠️ Known Limitations

* No semantic search yet (keyword-based only)
* Manual schema creation required
* No LLM integration out-of-the-box

---

## 💡 Vision

This is not just a knowledge base.

It is a step toward:

> **A persistent, evolving reasoning system for research and learning**

---

## 📜 License

MIT (or your preferred license)

---

## 🤝 Contributing

Contributions welcome:

* Schema improvements
* CLI extensions
* Agent integrations

---

## 👤 Author

Built as a foundation for LLM-driven research systems.

---

## ⭐ Final Thought

> Your knowledge shouldn't just be stored — it should **think with you**.
