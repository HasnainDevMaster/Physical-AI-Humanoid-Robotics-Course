# ADR-005: Accessibility Compliance Approach

- **Status**: Accepted
- **Date**: 2025-12-09
- **Drivers**:
  – Constitution success criteria: Lighthouse Accessibility >95
  – SVG diagrams must have descriptive alt text
  – Global student accessibility requirements
- **Context**:
  – Textbook must meet WCAG 2.1 AA standards for educational content
- **Options Considered**:
  – Manual accessibility auditing
  – Automated tooling with axe-core
  – Design system with built-in accessibility
  – Hybrid approach (automated + manual review)
- **Decision**:
  – Hybrid approach: Automated CI checks with axe-core + manual review for complex diagrams and interactions
- **Consequences**:
  + CI pipeline catches 90% of accessibility issues automatically
  + Lighthouse scores consistently >95 accessibility
  + Inclusive for students with disabilities
  – Additional review time required for complex diagrams
- **Bonus 1 Impact**: AccessibilitySkill validates content generation for compliance