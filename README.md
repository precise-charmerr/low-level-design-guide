# Complete Low-Level Design Interview Prep

A consolidated LLD / Object-Oriented Design / Machine Coding study repository assembled from two supplied repositories:

- `source/awesome-low-level-design` — broad OOP, SOLID, UML, design-pattern and multi-language problem collection.
- `source/kumaransg-LLD` — Java-heavy machine-coding and interview problem collection.

This repository **keeps the original material intact under `source/`** and adds a curated navigation/study layer under `00-study-guide/`. That avoids silently deleting useful implementations or overwriting one author's solution with another's.

## Start here

**If you want the shortest path:** start with [`00-study-guide/00-start-here.md`](00-study-guide/00-start-here.md), then do Parking Lot using [`00-study-guide/11-parking-lot-deep-dive.md`](00-study-guide/11-parking-lot-deep-dive.md).

1. Read [`00-study-guide/01-interview-flow.md`](00-study-guide/01-interview-flow.md)
2. Review [`00-study-guide/02-oop-solid.md`](00-study-guide/02-oop-solid.md)
3. Learn the patterns in [`00-study-guide/03-pattern-map.md`](00-study-guide/03-pattern-map.md)
4. Pick a problem from [`00-study-guide/04-problem-index.md`](00-study-guide/04-problem-index.md)
5. Before opening the solution, use [`00-study-guide/07-practice-template.md`](00-study-guide/07-practice-template.md)
6. For Java machine coding, use the material in `source/kumaransg-LLD`
7. Use the multi-language implementations in `source/awesome-low-level-design` for comparison and pattern recognition.

## Repository layout

```text
00-study-guide/                 Curated learning and interview material
source/
  awesome-low-level-design/     Original supplied repository, cleaned of IDE/build artifacts
  kumaransg-LLD/                Original supplied repository, cleaned of IDE/build artifacts
licenses/                       Preserved license/attribution information
```

## What was added

The added guide covers:

- A repeatable LLD interview workflow
- OOP + SOLID refresher
- Design-pattern decision map
- Problem index across both repositories
- Java-specific LLD checklist
- Concurrency topics worth knowing
- A reusable machine-coding practice template
- Common interview failure modes and follow-up questions
- A 14-day intensive practice plan
- Pattern-specific interview drills
- A Parking Lot deep dive and interview extension checklist
- A generated Java project catalog
- Small utility scripts for exploring the Java projects

## Important provenance note

The code/documentation in `source/` comes from the two repositories supplied for this merge. Their original license files and attribution material are retained where present. The newly added study-guide material is original compilation/organization for this combined repository.

Before redistributing the combined repository publicly, review the individual licenses in `licenses/` and any license files retained inside `source/`, especially where individual subprojects have their own licenses.

## Suggested learning order

```text
OOP
  ↓
SOLID
  ↓
Composition / inheritance / interfaces
  ↓
UML + class relationships
  ↓
Creational patterns
  ↓
Structural patterns
  ↓
Behavioral patterns
  ↓
Small LLDs
  ↓
Medium machine-coding problems
  ↓
Large machine-coding problems
  ↓
Timed implementation + design explanation
```
