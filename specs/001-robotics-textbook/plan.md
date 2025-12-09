# Implementation Plan: Physical AI & Humanoid Robotics Textbook

**Branch**: `001-robotics-textbook` | **Date**: 2025-12-09 | **Spec**: specs/001-robotics-textbook/spec.md
**Input**: Feature specification from `/specs/001-robotics-textbook/spec.md`

**Note**: This template is filled in by the `/sp.plan` command. See `.specify/templates/commands/plan.md` for the execution workflow.

## 1. Architecture Sketch

```
physical-ai-humanoid-robotics-course/
├── .github/
│   └── workflows/
│       └── ci.yml
├── docs/
│   ├── chapters/
│   │   ├── week-01-introduction-to-physical-ai/
│   │   ├── week-02-ros2-architecture-fundamentals/
│   │   ├── week-03-ros2-package-development/
│   │   ├── week-04-urdf-and-robot-description/
│   │   ├── week-05-ros2-controllers-and-rclpy/
│   │   ├── week-06-gazebo-simulation-fundamentals/
│   │   ├── week-07-sensor-simulation-and-unity/
│   │   ├── week-08-nvidia-isaac-sim-introduction/
│   │   ├── week-09-isaac-ros-and-hardware-acceleration/
│   │   ├── week-10-navigation-and-path-planning/
│   │   ├── week-11-humanoid-kinematics-and-locomotion/
│   │   ├── week-12-manipulation-and-grasping/
│   │   └── week-13-conversational-robotics/
│   ├── diagrams/
│   │   ├── architecture/
│   │   ├── data-flow/
│   │   └── kinematic-chains/
│   └── exercises/
├── src/
│   ├── python/
│   │   ├── ros_examples/
│   │   ├── gazebo_examples/
│   │   ├── isaac_examples/
│   │   └── vision_examples/
│   └── docker/
│       └── ros-humble/
├── .claude/
│   └── skills/
├── specs/
│   └── 001-robotics-textbook/
├── .specify/
├── history/
│   └── prompts/
├── docusaurus.config.js
├── package.json
├── tsconfig.json
├── babel.config.js
└── README.md
```

**Tech Stack:**
- Frontend: Docusaurus v3.9+, React 18, TypeScript strict mode, Tailwind CSS
- Backend: Python 3.10+, ROS 2 Humble, rclpy
- Simulation: Gazebo, NVIDIA Isaac Sim
- DevOps: Docker, GitHub Actions
- AI Orchestration: Claude Code subagents and skills
- Diagrams: SVG only

## 2. Mandatory Chapter Template

```mdx
---
title: "Week {N}: {Chapter Title}"
sidebar_label: "Week {N}: {Chapter Title}"
sidebar_position: {N}
description: "{Brief description of chapter content and learning outcomes}"
keywords: ["ROS 2", "Physical AI", "Robotics", "Week {N}"]
---

# Week {N}: {Chapter Title}

## Learning Objectives
- Objective 1 (specific, measurable outcome)
- Objective 2 (specific, measurable outcome)
- Objective 3 (specific, measurable outcome)

## Prerequisites
- Previous chapter concepts
- Specific tools or knowledge required

## Concepts (1500-2000 words)
### Section 1: {Subtopic}
Content explaining core concepts with examples.

### Section 2: {Subtopic}
Content building on previous section.

### Section 3: {Subtopic}
Advanced concepts and integration.

## Code Examples (800-1200 words)
### Example 1: {Description}
```python
# Executable code example
```

### Example 2: {Description}
```python
# Executable code example
```

## Exercise
Step-by-step hands-on exercise for students to complete.

## Quiz
5-8 multiple choice questions testing understanding.

## Further Reading
Links to official ROS 2/NVIDIA/Gazebo documentation.
```

**Word Count Allocation:**
- Learning Objectives: 50-100 words
- Prerequisites: 50-100 words
- Concepts: 1500-2000 words
- Code Examples: 800-1200 words
- Exercise: 300-400 words
- Quiz: 100-150 words
- Further Reading: 50-100 words
- Total: 4000-4500 words

## 3. Research & Citation Strategy

**Concurrent Research:**
- ROS 2 Humble API documentation and best practices
- NVIDIA Isaac Sim tutorials and examples
- Gazebo simulation patterns and best practices
- Physical AI implementation patterns
- Docusaurus v3.9+ features and customization

**Allowed Sources:**
- Official ROS 2 documentation (docs.ros.org)
- NVIDIA Isaac documentation (nvidia-isaac-sim.github.io)
- Gazebo documentation (gazebosim.org)
- Docusaurus documentation (docusaurus.io)
- Academic papers on Physical AI and humanoid robotics
- Industry whitepapers and technical reports

**Citation Format:**
```md
For technical claims: [Official ROS 2 documentation](https://docs.ros.org/en/humble/)
For concepts: [NVIDIA Isaac documentation](https://nvidia-isaac-sim.github.io)
For research: [Academic source with DOI]
```

## 4. Quality Gates & Automated Validation

**CI Checks:**
- `npm run build` - Build time < 60 seconds
- `npm run lint` - TypeScript strict mode compliance
- `linkinator docs/` - Zero broken links
- `npm run test` - Automated code example validation
- `lighthouse` - Performance >90, Accessibility >95

**Subagent-Enforced Rules:**
- Code examples must execute in Docker/Ubuntu 22.04
- SVG diagrams only (no PNG/JPG)
- MDX frontmatter validation
- Word count verification per chapter
- Code quality checks (Pylint, ESLint)

**Counters:**
- Chapter counter: 13 chapters required
- Code example counter: 80-120 examples
- SVG diagram counter: 65-91 diagrams
- Quiz question counter: 5-8 per chapter

## 5. Reusable Intelligence Inventory – Bonus 1

**Subagents:**
- `CodeGeneratorSubagent` - Generates executable Python/ROS code examples
  - Input: Technical requirement, ROS 2 Humble context
  - Output: Validated Python code with type hints and error handling

- `DiagramSubagent` - Creates SVG diagrams for concepts
  - Input: Diagram type (architecture, data flow, kinematic chain), description
  - Output: Accessible SVG with descriptive alt text

- `ExerciseSubagent` - Creates hands-on exercises
  - Input: Chapter topic, difficulty level, learning objectives
  - Output: Step-by-step guided exercise with validation steps

- `QuizSubagent` - Generates quiz questions
  - Input: Chapter content, learning objectives
  - Output: 5-8 multiple choice questions with explanations

**Skills:**
- `RosCodeSkill` - Reusable ROS 2 code templates and patterns
  - Input: Functionality requirement (publisher, subscriber, service, etc.)
  - Output: Ready-to-use ROS 2 code template

- `DiagramTemplateSkill` - SVG diagram templates for common robotics concepts
  - Input: Diagram type, customization parameters
  - Output: Ready-to-use SVG diagram template

- `ValidationSkill` - Automated testing for code examples
  - Input: Code example, execution environment
  - Output: Pass/fail result with error details

- `AccessibilitySkill` - Ensures content meets accessibility standards
  - Input: Content to validate
  - Output: Accessibility compliance report

## 6. Execution Phases & Timeline

**Phase 1: Foundation Setup (Days 1-2)**
- Set up Docusaurus project with TypeScript strict mode
- Configure Docker environment for ROS 2 Humble
- Implement Claude Code subagents and skills
- Create basic chapter template

**Phase 2: Module 1 - ROS 2 Fundamentals (Days 3-7)**
- Week 1: Introduction to Physical AI
- Week 2: ROS 2 Architecture Fundamentals
- Week 3: ROS 2 Package Development
- Week 4: URDF and Robot Description
- Week 5: ROS 2 Controllers and rclpy Integration

**Phase 3: Module 2 - Simulation Environments (Days 8-10)**
- Week 6: Gazebo Simulation Fundamentals
- Week 7: Sensor Simulation and Unity Integration

**Phase 4: Module 3 - NVIDIA Isaac (Days 11-14)**
- Week 8: NVIDIA Isaac Sim Introduction
- Week 9: Isaac ROS and Hardware-Accelerated Perception
- Week 10: Navigation and Path Planning

**Phase 5: Module 4 - Vision-Language-Action (Days 15-19)**
- Week 11: Humanoid Kinematics and Locomotion
- Week 12: Manipulation and Grasping
- Week 13: Conversational Robotics and VLA Integration

**Phase 6: Integration & Validation (Days 20-21)**
- Automated testing of all code examples
- Accessibility and performance validation
- Final build optimization for <60s build time
- Deployment to GitHub Pages

## 7. Testing & Success Criteria Mapping

**SC-001**: Students can build and deploy ROS 2 nodes after Week 5 → Automated test validates Week 5 code examples execute successfully in Docker/Ubuntu 22.04
**SC-002**: Students can simulate humanoid robots after Week 10 → Automated test validates Week 10 simulation examples run in Gazebo/Isaac Sim
**SC-003**: Students can integrate LLMs after Week 13 → Automated test validates Week 13 conversational robotics examples execute successfully
**SC-004**: All code examples execute with 100% success rate → CI pipeline validates all 80-120 code examples in Docker/Ubuntu 22.04
**SC-005**: Students can modify/extend examples with 95% success → Manual validation of extensibility with automated validation of core functionality
**SC-006**: 13 chapters with 4000-4500 words each → Automated word count validation for each chapter
**SC-007**: 80-120 code examples and 65-91 diagrams → Automated counter validation
**SC-008**: 80% retention rate → Simulated user testing metrics
**SC-009**: 80% of code/diagrams from subagents with 95% reuse → Subagent usage tracking and reuse validation
**SC-010**: >90% Lighthouse score → Automated Lighthouse CI check

**Acceptance Scenarios Mapping:**
- Given student completes Week 1, When reads Chapter 2 and completes examples, Then creates ROS 2 pub/sub → Week 2 automated test
- Given student reads Chapter 3, When follows exercises, Then creates ROS 2 package → Week 3 automated test
- Given student completed ROS 2 fundamentals, When works through Chapter 6, Then launches Gazebo worlds → Week 6 automated test
- Given student completed all chapters, When implements Chapter 13, Then builds voice-controlled robot → Week 13 automated test

## 8. ADRs Required Next

- **ADR-001: Docusaurus Architecture Decision** - Document choice of Docusaurus v3.9+ over other static site generators for robotics textbook
- **ADR-002: ROS 2 Humble Distribution Decision** - Document why ROS 2 Humble was chosen over other ROS 2 distributions
- **ADR-003: AI Orchestration Pattern** - Document Claude Code subagent architecture for content generation
- **ADR-004: Containerization Strategy** - Document Docker strategy for consistent code example execution
- **ADR-005: Accessibility Compliance Approach** - Document approach to meet >95 accessibility standards
