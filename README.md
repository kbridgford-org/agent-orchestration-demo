# Agent Orchestration: Sub-Agent Sequencing in VS Code

![Heroes Banner](media/heroes.png)

## Overview

This project demonstrates **agent orchestration with sub-agent sequencing** in Visual Studio Code — a pattern where a primary agent decomposes a complex prompt into discrete tasks and delegates each one to a specialized sub-agent, executed in sequence.

## The Demo

The orchestration is driven by a single, densely packed creative prompt ([prompt.md](prompt.md)) that describes **four parallel storylines**, each with a unique character, setting, and color identity:

| Character | Archetype | City | Color |
|-----------|------------|-----------|-------|
| **Atlas** | Powerhouse | Bastion | 🟢 Green |
| **Wraith** | Traumatized vigilante | Mist-Fall | 🔵 Blue |
| **Cipher** | Genius hacker | Neon-Grid | 🔴 Red |
| **Gideon** | Aristocrat | Lumina | ⚪ White |

A single prompt encodes all four storylines. The orchestrating agent parses the prompt, identifies the independent narrative threads, and sequences sub-agents to handle each one — demonstrating how VS Code's agent architecture can break down compound tasks and execute them methodically.

## How Sub-Agent Sequencing Works

```
┌─────────────────────────────────┐
│       Primary Agent             │
│  (Parses & decomposes prompt)   │
└────────────┬────────────────────┘
             │
             ▼
   ┌─────────────────┐
   │  Sub-Agent 1     │  → Atlas / Bastion / Green
   └────────┬────────┘
            ▼
   ┌─────────────────┐
   │  Sub-Agent 2     │  → Wraith / Mist-Fall / Blue
   └────────┬────────┘
            ▼
   ┌─────────────────┐
   │  Sub-Agent 3     │  → Cipher / Neon-Grid / Red
   └────────┬────────┘
            ▼
   ┌─────────────────┐
   │  Sub-Agent 4     │  → Gideon / Lumina / White
   └─────────────────┘
```

1. **Decomposition** — The primary agent reads the compound prompt and identifies four independent character arcs.
2. **Sequencing** — Each arc is delegated to a sub-agent in order. The output of one sub-agent can inform or constrain the next.
3. **Synthesis** — Results are collected and assembled into a cohesive output.

## Why Sequencing?

Unlike parallel fan-out, sequential sub-agent execution is ideal when:

- Later tasks depend on earlier results
- Output ordering matters
- You need deterministic, reproducible workflows
- Resource constraints require controlled execution

## Getting Started

1. Open this folder in VS Code
2. Open [prompt.md](prompt.md) in the editor
3. Use the Copilot agent to process the prompt and observe how it decomposes the task into sequential sub-agent calls

## Project Structure

```
├── README.md          ← You are here
├── prompt.md          ← The compound prompt driving the demo
└── media/
    └── heroes.png     ← Character art for the four heroes
```

## License

This project is provided as a demonstration for educational purposes.
