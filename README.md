# ResearchOS

### AI-Powered Research Workflow Automation

ResearchOS is an automated research workflow system built with **n8n** that transforms a research question into structured research insights and actionable research directions.

The system combines paper discovery, paper analysis, research synthesis, research gap discovery, and research direction generation into a modular workflow architecture.

---

## Project Overview

Research workflows often require researchers to manually perform repetitive tasks such as:

- Finding relevant academic papers
- Collecting research evidence
- Analysing papers
- Synthesising findings
- Identifying gaps in existing research
- Developing potential research directions

ResearchOS automates these stages through interconnected n8n workflows and AI-powered analysis.

---

## Architecture

The overall ResearchOS pipeline is:

Research Question  
↓  
Workspace Creation  
↓  
Paper Discovery  
↓  
Paper Analysis  
↓  
Research Synthesis  
↓  
Research Gap Discovery  
↓  
Research Direction Generation

The workflows communicate through structured JSON data and HTTP webhook interfaces.

---

## Core Workflows

### 1. Workspace Creation

Creates and validates a research workspace and returns a workspace identifier.

**Output:**
- `workspace_id`

---

### 2. Paper Discovery

Discovers relevant academic papers using external academic search services.

**Main components:**
- arXiv API
- Semantic Scholar API
- Search result aggregation
- Deduplication
- Supabase storage

**Output:**
- Structured list of discovered papers

---

### 3. Paper Analysis

Processes selected research papers and generates structured AI-assisted analysis.

**Main components:**
- Paper retrieval
- Content preparation
- OpenAI GPT-5-mini
- Output validation
- Supabase storage

**Output:**
- Structured paper analysis

---

### 4. Research Synthesis

Combines analysed research evidence and generates a structured synthesis.

The synthesis contains:
- Summary
- Key findings
- Research evidence

---

### 5. Research Gap Discovery

Uses the research synthesis to identify potential gaps in the existing literature.

**Output includes:**
- Gap summary
- Identified research gaps
- Supporting rationale

---

### 6. Research Direction Generation

Uses the research synthesis and identified gaps to generate concrete research directions.

Each direction contains:

- Research direction title
- Research question
- Rationale
- Expected contribution

---

## Technology Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow orchestration and automation |
| OpenAI GPT-5-mini | AI-powered research analysis |
| Supabase | Research data storage |
| arXiv API | Academic paper discovery |
| Semantic Scholar API | Academic paper discovery |
| Webhooks | Communication between workflow components |

---

## Workflow Design

ResearchOS follows a modular workflow architecture.

Each workflow generally contains:

1. Input webhook
2. Input normalization
3. Input validation
4. Processing / AI analysis
5. Output parsing
6. Output validation
7. Success response
8. Error handling

This structure allows individual workflows to be tested and reused independently.

---

## Error Handling

The workflows include validation and error-handling branches for invalid inputs and invalid AI outputs.

Examples include:

- Invalid request → validation error response
- Invalid AI output → analysis error response
- Valid AI output → structured success response

This prevents malformed AI responses from silently propagating through the research pipeline.

---

## Example Research Question

> How are autonomous AI agents being used for research?

ResearchOS can process this question through the research pipeline and produce:

**Research synthesis → Research gaps → Research directions**

---

## Project Deliverables

This repository contains:

- n8n workflow JSON definitions
- Workflow documentation
- ResearchOS architecture diagram
- Project README

---

## Running the Project

The workflows were developed using n8n.

To run the workflows:

1. Import the corresponding `.json` workflow into n8n.
2. Configure the required credentials.
3. Activate or execute the workflow.
4. Send the required JSON request to the workflow webhook.
5. Inspect the structured response.

API credentials are intentionally not included in this repository.

---

## Author

**Jiya Manaktala**

ResearchOS  
AI-Powered Research Workflow Automation
