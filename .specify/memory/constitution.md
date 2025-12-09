<!-- SYNC IMPACT REPORT
Version change: N/A (initial version) → 1.0.0
Modified principles: N/A
Added sections: Core Principles (6), Key Standards, Constraints, Success Criteria
Removed sections: N/A
Templates requiring updates:
  - .specify/templates/plan-template.md: ⚠ pending
  - .specify/templates/spec-template.md: ⚠ pending
  - .specify/templates/tasks-template.md: ⚠ pending
  - .specify/templates/commands/*.md: ⚠ pending
Follow-up TODOs: None
-->
# Physical AI & Humanoid Robotics Textbook Constitution

## Core Principles

### Code-First Pedagogy
Working examples before theory. All concepts must be demonstrated with executable code that students can run without modification.

### Progressive Scaffolding
Foundations → Implementation → Integration. Each chapter builds systematically on previous concepts while maintaining clear prerequisites for standalone learning.

### Industry Alignment
Alignment with industry-standard tools: ROS 2 Humble, NVIDIA Isaac, Gazebo. All examples and implementations must reflect current industry practices.

### Modular Design
Each chapter stands alone with clear prerequisites. Chapters must be independently accessible while forming a coherent learning progression.

### Executable Code Standards
Code examples must execute without modification. All Python code follows ROS 2 Humble standards with type hints and rclpy error handling; TypeScript follows Docusaurus v3.9+ with strict mode and Tailwind CSS.

### Accessibility and Documentation
Required MDX frontmatter (title, sidebar_label, sidebar_position, description); SVG diagrams only with descriptive alt text; citations must link to official ROS 2/NVIDIA documentation.

## Key Standards

Chapter structure: Objectives → Concepts (1500-2000 words) → Code (800-1200 words) → Exercise → Quiz. Python: ROS 2 Humble, type hints, rclpy error handling. TypeScript: Docusaurus v3.9+, strict mode, Tailwind CSS. MDX: Required frontmatter (title, sidebar_label, sidebar_position, description). Diagrams: SVG only, descriptive alt text for accessibility. Citations: Link to official ROS 2/NVIDIA docs for technical claims.

## Constraints

13 chapters total (Week 1-13 course structure). 4,000-4,500 words per chapter. 100+ executable code examples total. 80+ SVG diagrams. Node.js v18+. Build time under 60 seconds. Cross-platform: Windows development, Ubuntu 22.04 deployment target.

## Success Criteria

Zero build errors on GitHub Actions. All internal links resolve (linkinator verification). Code passes ESLint (TypeScript) and Pylint (Python). Lighthouse: Performance >90, Accessibility >95. Chapter exercises map 1:1 to learning objectives.

## Governance

This constitution governs all project decisions and supersedes any conflicting practices. All code, documentation, and examples must comply with these principles. Amendments require documentation of the change, justification for deviation from existing principles, and a migration plan for existing content. All pull requests must verify compliance with these standards before merging.

**Version**: 1.0.0 | **Ratified**: 2025-12-09 | **Last Amended**: 2025-12-09