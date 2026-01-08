# Agentic RAG with LangGraph

This project demonstrates an agentic Retrieval-Augmented Generation (RAG) system built using LangGraph.

Instead of a single prompt → response flow, this system models AI behavior as a stateful workflow where the model can:
- reason about user intent
- retrieve external context when needed
- route between specialized steps
- generate grounded responses

The goal is to move beyond prompt-level demos and explore how real AI systems coordinate reasoning, retrieval, and control flow.

---

## What This Project Does

At a high level, the pipeline:

1. Accepts a user question
2. Determines whether retrieval is required
3. Retrieves relevant context from a vector store (when needed)
4. Routes execution through an agentic graph
5. Generates a grounded response using retrieved context
6. Returns a final answer

This mirrors how production AI systems are designed:
LLMs as decision-makers, not just text generators.

---

## Architecture Overview

This project uses LangGraph to model the system as a graph of nodes:

- Input node – receives the user query
- Router node – decides whether retrieval is required
- Retriever node – fetches relevant documents via similarity search
- Generation node – produces a grounded response
- Terminal node – returns the final output

State is passed explicitly between nodes, making the system:
- inspectable
- debuggable
- extensible

---

## Why Agentic RAG Matters

Traditional RAG pipelines are linear:

query → retrieve → generate

Agentic RAG introduces control and reasoning:
- The model decides when retrieval is necessary
- Different steps can be reused or skipped
- Logic becomes explicit instead of hidden in prompts

This pattern is increasingly relevant for:
- enterprise knowledge systems
- decision support tools
- internal AI platforms
- multi-step reasoning workflows

---

## Tech Stack

- Python
- LangGraph
- LangChain
- OpenAI
- FAISS

---

## Files in This Repo

.
├── Agentic_RAG.ipynb
├── agentic_rag.py
└── README.md

---

## Key Concepts Demonstrated

- Agentic workflows vs linear pipelines
- Explicit state management in LLM systems
- Retrieval as a conditional step
- Separation of reasoning, retrieval, and generation
- System-level AI design

---

## Project Goal

This project is intentionally focused on architecture and system design, not polish.

The objective is to:
- understand how agentic RAG systems are composed
- explore LangGraph as a control-flow tool for LLMs
- build intuition for production-style AI workflows

This repo is part of a broader portfolio exploring RAG pipelines, multimodal systems, and applied AI engineering.

---

## Possible Extensions

Some natural next steps:
- Add multiple retriever types
- Introduce tool-calling nodes
- Add evaluation or logging steps
- Integrate memory or long-running state
- Wrap the graph in a lightweight API

---

If you’re interested in agentic RAG, LangGraph, or how LLM systems are designed beyond simple demos, feel free to explore or reach out.
