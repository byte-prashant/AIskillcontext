# 🧠 AI Skill Context & Prompt Engineering Guide

## 📌 Overview

This document explores how to design, manage, and optimize **AI skills, context, and prompt engineering** when building intelligent agents using LLMs.

It focuses on:

* Context window limitations
* Skill modularization
* Dynamic knowledge retrieval
* Memory and compression strategies

---

## 🧩 What are “Skills” in AI Agents?

A **skill** is a structured unit of knowledge or capability that helps an AI perform a specific task.

### Examples

* Debugging RTP issues in slot games
* Writing SQL queries
* Generating reports
* Analyzing logs

### Skill Structure

Each skill may contain:

* Instructions
* Examples
* Domain knowledge
* Constraints

---

## 📏 Optimal Size of Skills

### ⚠️ Problem

LLMs have a **limited context window**. When multiple skills are loaded:

* Older context gets forgotten
* Recent inputs dominate attention
* Performance degrades

### 💡 Key Insight

There is **no fixed optimal size**. It depends on:

* Model used
* Context window size
* Task complexity

### ✅ Best Practices

* Keep skills **modular and focused**
* Avoid large monolithic prompts
* Load only **task-relevant skills**

---

## 🧠 Core Challenges

### 1. Context Window Awareness

* How do we estimate available context?
* How much context is already consumed?

---

### 2. Skill Overload Problem

* Too many skills → exceeds context limit
* Model forgets earlier instructions

---

### 3. Knowledge Compression

* Can skills be compressed without losing meaning?

**Trade-off:**

* Smaller = faster + cheaper
* But may reduce clarity

---

### 4. Dynamic Skill Creation

* Can agents generate new skills automatically?
* Can they learn from past executions?

---

### 5. Storage & Retrieval

Where should skills be stored?

* Markdown / JSON files
* Databases
* Vector databases (for semantic search)

---

### 6. Skill Triggering Problem

* How does the system decide which skill to use?

---

## 🛠️ Proposed Solutions

### 1. Context Management

* Estimate tokens before execution
* Load only relevant skills

---

### 2. Skill Reintroduction

* Reload important skills when needed
* Keep skills stateless

---

### 3. Skill Compression

Convert verbose text into structured format:

```
IF RTP < expected:
  CHECK:
    - reel weights
    - RNG selection
    - feature triggers
```

---

### 4. Retrieval-Augmented Skills

* Store skills externally
* Fetch dynamically during execution

---

### 5. Hierarchical Skill Design

```
Master Skill
 ├── Debug RTP
 ├── Analyze Logs
 └── Optimize Game Math
```

---

### 6. Skill Execution Pipeline

```
User Query
   ↓
Intent Detection
   ↓
Skill Selection
   ↓
Skill Injection
   ↓
LL
```

### 7. Sequential thinking
     -- telling ai to not explore path, which has already been explored
     -- saving details of new path, results of previous path
