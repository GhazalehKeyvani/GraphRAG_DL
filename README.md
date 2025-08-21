# RAG Architecture Comparison for Technical Document QA

## Overview
This project implements and compares multiple Retrieval-Augmented Generation (RAG) architectures for querying complex technical documentation, specifically the MIL-PRF-19500/383B semiconductor specification standard.

## Experimental Results Summary

| Architecture | Accuracy | Precision@5 | Latency (s) | Best Use Case |
|--------------|----------|-------------|-------------|---------------|
| Dense (Baseline) | 60% | 70% | 0.8 | Simple fact retrieval |
| Hybrid | 75% | 85% | 1.2 | Balanced speed/accuracy |
| Graph-Based | 85% | 90% | 2.5 | Relationship-heavy queries |
| Graph + Hybrid Rerank | 95% | 95% | 3.8 | Highest accuracy requirements |

## Retrieval Method Comparison

**Question:** "What is the primary purpose of MIL-PRF-19500/383B?"

| Method | Output Summary | Strengths | Limitations |
|--------|----------------|-----------|-------------|
| **GraphRAG (Knowledge Graph)** | Comprehensive response with device types, quality levels, and DoD approval context | Rich context, explainable reasoning | Resource-intensive graph construction |
| **VectorRetriever** | Structured JSON with key specifications and test updates | Fast, simple, structured output | No explicit relationships |
| **Vector + Graph Traversal** | Factual core enhanced with relationship triples and relevant chunks | Higher recall, contextual links | Can surface verbose/irrelevant content |
| **Hybrid Retrieval** | Combined vector and keyword results with metadata | Balanced speed and coverage | Requires parameter tuning |
| **Hybrid + Graph Traversal** | Most comprehensive with multi-hop entities and references | Full contextual picture | Highest computational cost |

## Implementation Details
- Built with Neo4j Graph Database
- Utilizes vector indexing and semantic search
- Implements multi-hop reasoning capabilities
- Supports both structured and unstructured querying

## Key Findings
Graph-enhanced approaches show significant accuracy improvements (up to 95%) for technical document QA but require additional computational resources. The optimal architecture depends on specific use case requirements for speed versus comprehensiveness.

For complete implementation code and detailed evaluation metrics, see the accompanying Jupyter notebook and technical report.
