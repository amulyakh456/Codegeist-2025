# Why — Decision Memory for Atlassian

> **Codegeist 2025: Atlassian Williams Racing Edition**  
> Category: Apps for Software Teams

## The Problem

Every team makes hundreds of decisions—in Jira comments, PR reviews, Confluence discussions, Slack threads. Six months later, someone asks:

*"Why did we choose Postgres over MongoDB?"*  
*"Who decided to deprecate the v1 API?"*  
*"What was the reasoning behind this architecture?"*

Nobody knows. The context is gone. The same debates happen again. New team members are lost.

**Decisions are made everywhere. They're remembered nowhere.**

## The Solution

**Why** is a Rovo agent that captures decision context automatically and makes it searchable forever.

### How It Works

1. **Detects decisions** — Watches Jira issues, Confluence pages, and Bitbucket PRs for decision signals ("we decided", "let's go with", "the conclusion is", etc.)

2. **Prompts for context** — When a decision is detected, asks: "Looks like a decision was made. Want to capture why?"

3. **Stores decision memory** — Saves the decision, reasoning, who made it, when, and links to related issues/docs/code

4. **Answers questions** — Ask the agent anything:
   - "Why did we choose this database?"
   - "What decisions have we made about authentication?"
   - "Show me all architecture decisions from Q3"

## Features

 **Decision Detection** — AI-powered recognition of decision language in comments and discussions
 **Conversational Capture** — Natural chat interface to add context and reasoning
 **Cross-Product Links** — Connects decisions to Jira issues, Confluence pages, Bitbucket PRs
 **Searchable Memory** — Query past decisions in natural language
 **Decision Timeline** — Visual history of what was decided and when 
 **Team Awareness** — See who made decisions and who was involved

## Tech Stack

- **Atlassian Forge** — Serverless app platform
- **Rovo Agent** — Conversational AI interface
- **Forge Storage** — Persistent decision database
- **Jira/Confluence/Bitbucket APIs** — Cross-product integration

## Installation

### Prerequisites

- Node.js 18+
- Atlassian Cloud developer account
- Forge CLI

### Setup

```bash
# Install Forge CLI
npm install -g @forge/cli

# Login to Atlassian
forge login

# Install dependencies
npm install

# Deploy to development
forge deploy

# Install on your Atlassian site
forge install
```

### Configuration

1. Install the app on your Atlassian site
2. Navigate to Rovo Chat
3. Find "Why" in the agent directory
4. Start capturing decisions

## Usage

### Capturing a Decision

When Why detects a decision in your workflow:

```
Why: I noticed you wrote "Let's go with Redis for caching" in PROJ-123.
     Want to capture why this decision was made?

You: Yes, we chose Redis because we need sub-millisecond latency 
     and our team already has Redis expertise.

Why: Got it. I've saved this decision and linked it to PROJ-123.
     Anything else to add about alternatives considered?

You: We also looked at Memcached but Redis has better data structures.

Why: Decision captured with full context. ✓
```

### Querying Past Decisions

```
You: Why did we choose Redis?

Why: On March 15, 2025, the team decided to use Redis for caching.

     Reasoning: Sub-millisecond latency requirements, existing team expertise.
     
     Alternatives considered: Memcached (rejected due to limited data structures)
     
     Decision made by: @sarah in PROJ-123
     Related: [PROJ-123] [Architecture Doc] [PR #456]
```





Built for Codegeist 2025 by Amulya K H



MIT
