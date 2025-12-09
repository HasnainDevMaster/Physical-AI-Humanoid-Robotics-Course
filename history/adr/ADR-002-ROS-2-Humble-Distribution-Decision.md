# ADR-002: ROS 2 Humble Distribution Decision

- **Status**: Accepted
- **Date**: 2025-12-09
- **Drivers**:
  – Constitution explicitly locks to ROS 2 Humble
  – Industry alignment requirement
  – Must match Ubuntu 22.04 deployment target
- **Context**:
  – Students must run code unmodified — newer distributions break compatibility
- **Options Considered**:
  – ROS 2 Humble (2022 LTS)
  – ROS 2 Iron Irwini / Jazzy Jalisco / Kilted
- **Decision**:
  – Lock permanently to ROS 2 Humble Hawksbill for the entire textbook
- **Consequences**:
  + Maximum stability and reproducibility for students until at least 2027
  + Matches 95 % of current industry humanoid deployments in 2025
  – Misses some newer navigation2/features (will be noted as "future work" in Week 13)
- **Bonus 1 Impact**: CodeGenSkill can be hard-coded to Humble conventions → higher reliability