# 🧠 AI Content Vault

> An AI-powered personal content management platform that lets you save online content and find it later using natural-language descriptions.

🔗 **Live Demo:** https://aicontentvault.site

---

## 📌 Overview

AI Content Vault is a full-stack web application designed to solve a simple but common problem:

> **"I saved that video somewhere... but I can't remember where."**

People save hundreds of Reels, YouTube videos, GitHub repositories, articles, and other links, but traditional bookmarks and folders make it difficult to find something when you only remember what the content was about.

AI Content Vault combines **semantic search, embeddings, and RAG** to allow users to search their saved content based on meaning rather than exact keywords.

For example:

> "Find that video where someone explains how to make better coffee at home."

The system can retrieve relevant saved content even when the exact words from the query don't appear in the title.

---

## ✨ Features

- 🔗 Save content from multiple platforms
- 🤖 AI-powered semantic search
- 🧠 RAG-based content retrieval
- 🔍 Search using natural-language descriptions
- 📝 Add personal notes to saved content
- ⭐ Favorite saved content
- 🖼️ Automatically retrieve available metadata and thumbnails
- 🔐 User authentication
- ⚡ Redis-based API rate limiting
- 📱 Responsive interface
- 🚀 Production deployment with Vercel

### Supported Platforms

- YouTube
- Instagram
- GitHub
- Twitter/X
- LinkedIn
- Medium
- Other URLs

---

# 🏗️ System Architecture

```text
                         ┌─────────────────────┐
                         │       User          │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │   Next.js Frontend  │
                         │                     │
                         │ React + Tailwind    │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │   Backend / APIs    │
                         │                     │
                         │ Authentication      │
                         │ Content Management  │
                         │ Search              │
                         │ Rate Limiting       │
                         └──────┬───────┬──────┘
                                │       │
                    ┌───────────┘       └────────────┐
                    ▼                                ▼
             ┌─────────────┐                  ┌─────────────┐
             │  MongoDB    │                  │   Redis     │
             │             │                  │             │
             │ Content     │                  │ Rate Limits │
             │ Metadata    │                  │ Caching     │
             │ Embeddings  │                  │             │
             └──────┬──────┘                  └─────────────┘
                    │
                    ▼
             ┌─────────────┐
             │ Vector      │
             │ Search      │
             │             │
             │ Embeddings  │
             └──────┬──────┘
                    │
                    ▼
             ┌─────────────┐
             │ Gemini      │
             │             │
             │ Embeddings  │
             │ AI / RAG    │
             └─────────────┘
