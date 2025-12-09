# ADR-004: Containerization Strategy

- **Status**: Accepted
- **Date**: 2025-12-09
- **Drivers**:
  – Constitution: "Code examples must execute without modification"
  – Cross-platform requirement (Windows dev → Ubuntu 22.04 target)
  – 100 % reproducible student environment
- **Context**:
  – Students have varied hardware (CPU-only laptops vs GPU workstations)
- **Options Considered**:
  – Bare-metal Ubuntu instructions
  – Devcontainer only
  – Docker Compose with pre-built ROS Humble + Gazebo + Isaac Sim ready
- **Decision**:
  – Single docker-compose.yml with three profiles: minimal (CPU), gazebo, isaac-sim
- **Consequences**:
  + One-command `docker compose up minimal` works for every student
  + CI can spin up identical environment for automated testing
  – Slightly larger repo size (mitigated by .dockerignore)
- **Bonus 1 Impact**: CodeGenSkill outputs Docker-ready snippets automatically