---
description: "Task list for Physical AI & Humanoid Robotics Textbook implementation"
---

# Tasks: Physical AI & Humanoid Robotics Textbook

**Input**: Design documents from `/specs/001-robotics-textbook/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, contracts/

**Tests**: The examples below include test tasks. Tests are OPTIONAL - only include them if explicitly requested in the feature specification.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Documentation project**: `docs/`, `src/`, `docusaurus.config.js`, `package.json`

<!--
  ============================================================================
  IMPORTANT: The tasks below are actual tasks based on:
  - User stories from spec.md (with their priorities P1, P2, P3...)
  - Feature requirements from plan.md
  - Entities from spec.md
  - Success criteria from spec.md

  Tasks are organized by user story so each story can be:
  - Implemented independently
  - Tested independently
  - Delivered as an MVP increment
  ============================================================================
-->

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Project initialization and basic structure

- [ ] T001 [P] Create Docusaurus project structure per implementation plan in docs/
- [ ] T002 [P] Initialize Node.js project with Docusaurus v3.9+ dependencies in package.json
- [ ] T003 [P] Configure TypeScript strict mode and Tailwind CSS in tsconfig.json and docusaurus.config.js
- [ ] T004 [P] Set up Docker environment for ROS 2 Humble in src/docker/ros-humble/
- [ ] T005 [P] Configure GitHub Actions CI workflow in .github/workflows/ci.yml
- [ ] T006 [P] Create basic chapter template in docs/chapters/template.mdx

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Core infrastructure that MUST be complete before ANY user story can be implemented

**⚠️ CRITICAL**: No user story work can begin until this phase is complete

- [ ] T007 Set up Claude Code subagents and skills in .claude/skills/
- [ ] T008 [P] Configure CI checks for build time < 60s in .github/workflows/ci.yml
- [ ] T009 [P] Set up link validation for zero broken links in .github/workflows/ci.yml
- [ ] T010 [P] Configure Lighthouse CI checks for >90 performance, >95 accessibility in .github/workflows/ci.yml
- [ ] T011 [P] Set up automated code example validation in .github/workflows/ci.yml
- [ ] T012 [P] Create SVG diagram templates in docs/diagrams/architecture/, docs/diagrams/data-flow/, docs/diagrams/kinematic-chains/
- [ ] T013 Configure Docusaurus sidebar and navigation in docusaurus.config.js

**Checkpoint**: Foundation ready - user story implementation can now begin in parallel

---

## Phase 3: User Story 1 - Student Learns ROS 2 Fundamentals (Priority: P1) 🎯 MVP

**Goal**: Enable students to learn ROS 2 architecture fundamentals by Week 5, building and deploying ROS 2 nodes for robot control

**Independent Test**: Students can complete Week 2-5 content and successfully create a multi-node ROS 2 system with publisher/subscriber communication that demonstrates their understanding of the core concepts

### Implementation for User Story 1

- [ ] T014 [P] [US1] Create Week 1 Introduction to Physical AI chapter in docs/chapters/week-01-introduction-to-physical-ai/index.mdx
- [ ] T015 [P] [US1] Create Week 2 ROS 2 Architecture Fundamentals chapter in docs/chapters/week-02-ros2-architecture-fundamentals/index.mdx
- [ ] T016 [P] [US1] Create Week 3 ROS 2 Package Development chapter in docs/chapters/week-03-ros2-package-development/index.mdx
- [ ] T017 [P] [US1] Create Week 4 URDF and Robot Description chapter in docs/chapters/week-04-urdf-and-robot-description/index.mdx
- [ ] T018 [P] [US1] Create Week 5 ROS 2 Controllers and rclpy Integration chapter in docs/chapters/week-05-ros2-controllers-and-rclpy/index.mdx
- [ ] T019 [P] [US1] Create ROS 2 code examples in src/python/ros_examples/
- [ ] T020 [P] [US1] Create ROS 2 executable code examples with type hints and error handling in src/python/ros_examples/
- [ ] T021 [US1] Create automated test suite for Week 5 ROS 2 examples in src/python/ros_examples/test_week5.py
- [ ] T022 [US1] Create SVG diagrams for ROS 2 architecture in docs/diagrams/architecture/ros2-architecture.svg
- [ ] T023 [US1] Create SVG diagrams for nodes/topics/services in docs/diagrams/data-flow/ros2-nodes-topics.svg
- [ ] T024 [US1] Create executable ROS 2 node examples with pub/sub communication in src/python/ros_examples/pubsub_example.py
- [ ] T025 [US1] Create custom ROS 2 package example with configurable nodes in src/python/ros_examples/custom_package_example.py
- [ ] T026 [US1] Validate all code examples execute successfully in Docker/Ubuntu 22.04 environment (run automated test suite; confirm 100% success rate for all ROS 2 examples)

**Checkpoint**: At this point, User Story 1 should be fully functional and testable independently

---

## Phase 4: User Story 2 - Student Masters Simulation Environments (Priority: P2)

**Goal**: Enable students to learn to simulate humanoid robots in Gazebo and NVIDIA Isaac Sim by Week 10

**Independent Test**: Students can complete Week 6-7 content and successfully create custom Gazebo worlds with humanoid robots, configure physics engines, and process simulated sensor data

### Implementation for User Story 2

- [ ] T027 [P] [US2] Create Week 6 Gazebo Simulation Fundamentals chapter in docs/chapters/week-06-gazebo-simulation-fundamentals/index.mdx
- [ ] T028 [P] [US2] Create Week 7 Sensor Simulation and Unity Integration chapter in docs/chapters/week-07-sensor-simulation-and-unity/index.mdx
- [ ] T029 [P] [US2] Create Gazebo code examples in src/python/gazebo_examples/
- [ ] T030 [P] [US2] Create Gazebo simulation examples with physics engines in src/python/gazebo_examples/
- [ ] T031 [US2] Create automated test suite for Week 10 simulation examples in src/python/gazebo_examples/test_week10.py
- [ ] T032 [US2] Create SVG diagrams for Gazebo simulation architecture in docs/diagrams/architecture/gazebo-simulation.svg
- [ ] T033 [US2] Create SVG diagrams for sensor simulation data flow in docs/diagrams/data-flow/sensor-simulation.svg
- [ ] T034 [US2] Create custom Gazebo world example with humanoid robot in src/python/gazebo_examples/custom_world_example.py
- [ ] T035 [US2] Create physics engine configuration examples (ODE/Bullet) in src/python/gazebo_examples/physics_config_example.py
- [ ] T036 [US2] Create simulated sensor data processing examples in src/python/gazebo_examples/sensor_processing_example.py
- [ ] T037 [US2] Validate all simulation examples run successfully in Gazebo environment (execute test scripts; confirm Gazebo launches with <5s startup and sensor data logs match expected output)

**Checkpoint**: At this point, User Stories 1 AND 2 should both work independently

---

## Phase 5: User Story 3 - Student Integrates LLMs with Robotic Systems (Priority: P3)

**Goal**: Enable students to learn to integrate Large Language Models with robotic systems by Week 13, building voice-controlled robots

**Independent Test**: Students can complete Week 13 content and successfully build a voice-controlled robot that executes multi-step tasks from natural language commands

### Implementation for User Story 3

- [ ] T041 [P] [US3] Create Week 8 NVIDIA Isaac Sim Introduction chapter in docs/chapters/week-08-nvidia-isaac-sim-introduction/index.mdx
- [ ] T042 [P] [US3] Create Week 9 Isaac ROS and Hardware-Accelerated Perception chapter in docs/chapters/week-09-isaac-ros-and-hardware-acceleration/index.mdx
- [ ] T043 [P] [US3] Create Week 10 Navigation and Path Planning chapter in docs/chapters/week-10-navigation-and-path-planning/index.mdx
- [ ] T039 [P] [US3] Create Week 11 Humanoid Kinematics and Locomotion chapter in docs/chapters/week-11-humanoid-kinematics-and-locomotion/index.mdx
- [ ] T040 [P] [US3] Create Week 12 Manipulation and Grasping chapter in docs/chapters/week-12-manipulation-and-grasping/index.mdx
- [ ] T038 [P] [US3] Create Week 13 Conversational Robotics chapter in docs/chapters/week-13-conversational-robotics/index.mdx
- [ ] T044 [P] [US3] Create Isaac Sim code examples in src/python/isaac_examples/
- [ ] T045 [P] [US3] Create LLM integration examples in src/python/vision_examples/
- [ ] T046 [US3] Create automated test suite for Week 13 LLM integration examples in src/python/vision_examples/test_week13.py
- [ ] T047 [US3] Create SVG diagrams for conversational robotics architecture in docs/diagrams/architecture/conversational-robotics.svg
- [ ] T048 [US3] Create SVG diagrams for LLM-to-action data flow in docs/diagrams/data-flow/llm-action-flow.svg
- [ ] T049 [US3] Create voice-controlled robot example in src/python/vision_examples/voice_robot_example.py
- [ ] T050 [US3] Create natural language to action translation example in src/python/vision_examples/nlp_translation_example.py
- [ ] T051 [US3] Create multi-step task execution example in src/python/vision_examples/multi_step_task_example.py
- [ ] T052 [US3] Validate all conversational robotics examples execute successfully in target environment (run full LLM pipeline test; confirm 80% success rate on multi-step task execution with sample inputs)

**Checkpoint**: All user stories should now be independently functional

---

## Phase 6: Bonus Enhancements Implementation

**Goal**: Implement reusable intelligence via Claude Code subagents/skills for enhanced book generation

### Implementation for Bonus Enhancements

- [ ] T053 [P] [BONUS] Implement CodeGeneratorSubagent in .claude/skills/code-generator.skill
- [ ] T054 [P] [BONUS] Implement DiagramSubagent in .claude/skills/diagram-generator.skill
- [ ] T055 [P] [BONUS] Implement ExerciseSubagent in .claude/skills/exercise-generator.skill
- [ ] T056 [P] [BONUS] Implement QuizSubagent in .claude/skills/quiz-generator.skill
- [ ] T057 [P] [BONUS] Implement RosCodeSkill in .claude/skills/ros-code.skill
- [ ] T058 [P] [BONUS] Implement DiagramTemplateSkill in .claude/skills/diagram-template.skill
- [ ] T059 [P] [BONUS] Implement ValidationSkill in .claude/skills/validation.skill
- [ ] T060 [P] [BONUS] Implement AccessibilitySkill in .claude/skills/accessibility.skill
- [ ] T061 [BONUS] Integrate subagents with book generation process
- [ ] T062 [BONUS] Validate 80% of code/diagrams generated by subagents with 95% reuse rate (run subagent usage tracking script; confirm metrics meet targets)

---

## Phase 7: Polish & Cross-Cutting Concerns

**Purpose**: Improvements that affect multiple user stories

- [ ] T063 [P] Validate all 13 chapters have 4000-4500 words each using word counting tool (run word_count.py script; confirm all chapters in range)
- [ ] T064 [P] Validate all 100+ code examples execute successfully in Docker/Ubuntu 22.04 environment (run GitHub Actions CI; confirm 100% colcon test pass rate for all examples)
- [ ] T065 [P] Validate all 80+ SVG diagrams are accessible with descriptive alt text (run accessibility checker; confirm Lighthouse A11y >95 and all SVGs have descriptive alt text)
- [ ] T066 [P] Validate all 5-8 quiz questions per chapter exist in each chapter (run quiz validation script; confirm count and format per chapter)
- [ ] T067 [P] Validate all exercises have step-by-step guided implementation (run exercise validation script; confirm each chapter has complete step-by-step instructions)
- [ ] T068 [P] Validate all further reading links to official ROS 2/NVIDIA/Gazebo documentation (run link validation script; confirm all links resolve to official docs)
- [ ] T069 [P] Run accessibility validation with Lighthouse >95 score (execute lighthouse CI checks; confirm accessibility score >95 across all pages)
- [ ] T070 [P] Run performance validation with Lighthouse >90 score (execute lighthouse CI checks; confirm performance score >90 across all pages)
- [ ] T071 [P] Run build time validation <60 seconds (execute `npm run build`; confirm build completes in under 60 seconds)
- [ ] T072 [P] Run link validation to ensure zero broken links (execute `linkinator docs/`; confirm 100% of internal links resolve successfully)
- [ ] T073 [P] Update README.md with project documentation
- [ ] T074 [P] Create deployment configuration for GitHub Pages

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies - can start immediately
- **Foundational (Phase 2)**: Depends on Setup completion - BLOCKS all user stories
- **User Stories (Phase 3+)**: All depend on Foundational phase completion
  - User stories can then proceed in parallel (if staffed)
  - Or sequentially in priority order (P1 → P2 → P3)
- **Bonus Enhancements (Phase 6)**: Can run in parallel with user stories or after
- **Polish (Final Phase)**: Depends on all desired user stories being complete

### User Story Dependencies

- **User Story 1 (P1)**: Can start after Foundational (Phase 2) - No dependencies on other stories
- **User Story 2 (P2)**: Can start after Foundational (Phase 2) - May integrate with US1 but should be independently testable
- **User Story 3 (P3)**: Can start after Foundational (Phase 2) - May integrate with US1/US2 but should be independently testable

### Within Each User Story

- Core implementation before integration
- Story complete before moving to next priority

### Parallel Opportunities

- All Setup tasks marked [P] can run in parallel
- All Foundational tasks marked [P] can run in parallel (within Phase 2)
- Once Foundational phase completes, all user stories can start in parallel (if team capacity allows)
- Models within a story marked [P] can run in parallel
- Different user stories can be worked on in parallel by different team members
- Bonus enhancements can run in parallel with user stories

---

## Parallel Example: User Story 1

```bash
# Launch all Week 1-5 chapters together:
Task: "Create Week 1 Introduction to Physical AI chapter in docs/chapters/week-01-introduction-to-physical-ai/index.mdx"
Task: "Create Week 2 ROS 2 Architecture Fundamentals chapter in docs/chapters/week-02-ros2-architecture-fundamentals/index.mdx"
Task: "Create Week 3 ROS 2 Package Development chapter in docs/chapters/week-03-ros2-package-development/index.mdx"
Task: "Create Week 4 URDF and Robot Description chapter in docs/chapters/week-04-urdf-and-robot-description/index.mdx"
Task: "Create Week 5 ROS 2 Controllers and rclpy Integration chapter in docs/chapters/week-05-ros2-controllers-and-rclpy/index.mdx"

# Launch all ROS 2 code examples together:
Task: "Create ROS 2 code examples in src/python/ros_examples/"
Task: "Create ROS 2 executable code examples with type hints and error handling in src/python/ros_examples/"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup
2. Complete Phase 2: Foundational (CRITICAL - blocks all stories)
3. Complete Phase 3: User Story 1
4. **STOP and VALIDATE**: Test User Story 1 independently
5. Deploy/demo if ready

### Incremental Delivery

1. Complete Setup + Foundational → Foundation ready
2. Add User Story 1 → Test independently → Deploy/Demo (MVP!)
3. Add User Story 2 → Test independently → Deploy/Demo
4. Add User Story 3 → Test independently → Deploy/Demo
5. Each story adds value without breaking previous stories

### Parallel Team Strategy

With multiple developers:

1. Team completes Setup + Foundational together
2. Once Foundational is done:
   - Developer A: User Story 1
   - Developer B: User Story 2
   - Developer C: User Story 3
   - Developer D: Bonus Enhancements
3. Stories complete and integrate independently

---

## Notes

- [P] tasks = different files, no dependencies
- [Story] label maps task to specific user story for traceability
- Each user story should be independently completable and testable
- Commit after each task or logical group
- Stop at any checkpoint to validate story independently
- Validate all code examples execute in Docker/Ubuntu 22.04 environment
- Validate all diagrams are SVG format with accessibility features
- Validate all chapters meet 4000-4500 word requirement
- Validate build completes in under 60 seconds