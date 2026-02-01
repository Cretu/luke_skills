# Memoir Agent Skills

A collection of Claude Agent Skills for creating personal memoirs through a structured three-phase workflow.

## Skills

### 1. memoir-memory-recall
Extract personal memories through structured questioning without generating narrative prose.

**Purpose**: Help users remember details, not write them.

### 2. memoir-architect-biographer
Guide memoir structure, create chapter outlines, and validate content consistency.

**Purpose**: Organize memories into coherent narrative arcs.

### 3. memoir-writing
Transform memories and structure into restrained, literary memoir prose.

**Purpose**: Craft vivid scenes that honor the original experience.

## Workflow

```
Memory Recall → Architect/Biographer → Writing
```

See [orchestration.md](orchestration.md) for detailed coordination guidelines.

## Directory Structure

```
memoir-agent-skills/
├── orchestration.md              # Workflow coordination
├── .claude/
│   └── skills.json              # Claude configuration
├── memoir-memory-recall/
│   ├── SKILL.md                 # Skill definition
│   ├── SKILL.yaml               # Extended config (optional)
│   ├── reference.md             # Usage guidelines
│   ├── prompts/                 # Question templates
│   └── EXAMPLES.md              # Usage examples
├── memoir-architect-biographer/
│   ├── SKILL.md
│   ├── SKILL.yaml
│   ├── reference.md
│   ├── prompts/
│   └── EXAMPLES.md
└── memoir-writing/
    ├── SKILL.md
    ├── SKILL.yaml
    ├── reference.md
    ├── prompts/
    └── EXAMPLES.md
```

## Usage

Each skill can be used independently or as part of the full workflow. See individual skill directories for detailed documentation.
