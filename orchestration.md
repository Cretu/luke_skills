# Memoir Skills Orchestration

This document defines how `memoir-memory-recall`, `memoir-architect-biographer`, and `memoir-writing` are coordinated to create a complete memoir writing workflow.

## Overview

The three skills form a sequential pipeline:

```
┌─────────────────┐    ┌─────────────────────┐    ┌─────────────────┐
│  Memory Recall  │ →  │  Architect/Biographer│ →  │  Memoir Writing │
│  (extract)      │    │  (structure)        │    │  (craft)        │
└─────────────────┘    └─────────────────────┘    └─────────────────┘
```

## Phase 1: Memory Recall

**Skill**: `memoir-memory-recall`

**Goal**: Extract raw memories with sensory detail and emotional context.

**What it does**:
- Guides user through structured recall questions
- Documents specific moments, people, places
- Preserves details without interpretation
- Builds a memory inventory

**Output**: Raw memory notes with context, sensory details, and emotional notes

**When to use**:
- User wants to explore a specific time period
- User has fragmented memories to organize
- User needs help triggering deeper recall

## Phase 2: Structure Design

**Skill**: `memoir-architect-biographer`

**Goal**: Transform raw memories into a coherent memoir structure.

**What it does**:
- Identifies thematic threads across memories
- Creates chapter outlines with clear purposes
- Validates timeline consistency
- Ensures emotional arc coherence

**Output**: Chapter outline with themes, time periods, and key moments

**When to use**:
- After sufficient memories have been recalled
- User needs help organizing scattered memories
- User is ready to think about book structure

## Phase 3: Writing

**Skill**: `memoir-writing`

**Goal**: Craft raw memories and approved structure into literary prose.

**What it does**:
- Transforms bullet-point memories into scenes
- Applies restrained memoir voice
- Balances scene, action, and aftermath
- Maintains consistent tone throughout

**Output**: Polished prose chapters

**When to use**:
- Memory recall is complete
- Structure has been approved
- User wants to see memories as written passages

## Coordination Patterns

### Linear Pipeline (Recommended)
For users starting from scratch:

1. Use `memoir-memory-recall` to explore key periods
2. Use `memoir-architect-biographer` to organize findings
3. Use `memoir-writing` to draft chapters

### Iterative Mode
For refinement within a chapter:

1. Recall more details about specific moments
2. Update structure if needed
3. Rewrite passage with new details

### Parallel Exploration
For non-linear approaches:

1. Recall memories for multiple chapters simultaneously
2. Periodically use `memoir-architect-biographer` to reorganize
3. Write completed chapters as ready

## Data Flow

```
User Input
    │
    ▼
┌───────────────────┐
│ Memory Recall     │  →  Memory Inventory (JSON/Markdown)
└───────────────────┘
    │
    ▼
┌───────────────────┐
│ Architect/Bio     │  →  Chapter Outline (Markdown)
└───────────────────┘
    │
    ▼
┌───────────────────┐
│ Writing           │  →  Completed Chapters (Markdown)
└───────────────────┘
```

## File Management Strategy (Context Control)

To prevent context window overflow and ensure consistency:

1.  **Atomic Memory Files**: Save the output of `memoir-memory-recall` into separate files per topic/era (e.g., `memories/childhood_home.md`).
2.  **Selective Context Loading**: When running `memoir-writing`:
    *   Load the **Chapter Outline** (for global context).
    *   Load the **Style Sample** (for voice consistency).
    *   Load **ONLY** the specific memory files relevant to the current chapter.
    *   *Do not* load the entire memory inventory.

## Execution Modes

### 🚀 Quick Start (Linear)
Best for users who want to see results fast.
1.  Recall **one** specific, vivid memory (10 mins).
2.  Skip the full biography outline.
3.  Write a **single standalone vignette** based on that memory.

### 🏗️ Deep Architect (Holistic)
Best for users committed to a full book.
1.  Spend multiple sessions purely on Recall across different life eras.
2.  Build a comprehensive Outline.
3.  Write chapters systematically.

## Transition Guidelines

### Between Recall and Architecture
- Confirm user has explored key life periods
- Ensure enough raw material exists for chapters
- Ask: "What period feels most important to start with?"

### Between Architecture and Writing
- Review and approve chapter outline
- Confirm which chapter to write first
- Select specific memories for each chapter

### Within Any Phase
- User can return to earlier phases at any time
- Memories can be added to any chapter
- Structure can be revised as new memories emerge

## Best Practices

1. **Don't rush phases**: Each phase serves a distinct purpose
2. **Document everything**: Raw memories inform all later work
3. **Stay in phase**: Writing skill should not do recalling
4. **Iterate freely**: Return to earlier phases as needed
5. **Trust the process**: Each phase builds on the previous
