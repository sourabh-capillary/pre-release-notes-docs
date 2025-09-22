# Pre-Release Notes Documentation Repository

## Overview

This repository serves as a centralized documentation hub for Capillary's sprint-based development process. It contains Product Requirements Documents (PRDs), Technical Documentation, and general documentation that will be automatically processed to generate release notes when Jira tickets are closed.

## Repository Structure

```
pre-release-notes-docs/
├── sprint-2024-01/          # Sprint-specific folder
│   ├── PRDs/               # Product Requirements Documents
│   ├── Tech-docs/          # Technical Documentation
│   └── Docs/               # General Documentation
├── sprint-2024-02/          # Next sprint folder
│   ├── PRDs/
│   ├── Tech-docs/
│   └── Docs/
└── README.md               # This file
```

## Workflow

### 1. Sprint Documentation Phase
- **Timeline**: During each sprint
- **Action**: Team members populate the sprint-specific folder with documentation
- **Structure**: Create a folder named after the sprint (e.g., `sprint-2024-01`, `sprint-2024-02`) with three subfolders

### 2. Documentation Types

#### PRDs (Product Requirements Documents)
- **Location**: `[sprint-name]/PRDs/`
- **Content**: 
  - Feature specifications
  - User stories
  - Acceptance criteria
  - Business requirements
  - Product decisions

#### Tech-docs (Technical Documentation)
- **Location**: `[sprint-name]/Tech-docs/`
- **Content**:
  - Architecture changes
  - API documentation
  - Database schema changes
  - Technical specifications
  - Code documentation
  - Infrastructure changes

#### Docs (General Documentation)
- **Location**: `[sprint-name]/Docs/`
- **Content**:
  - Process documentation
  - Configuration changes
  - Deployment notes
  - User guides
  - Training materials

### 3. Automated Release Notes Generation
- **Trigger**: When Jira tickets for a sprint are closed
- **Process**: Bot automatically fetches documentation from the corresponding sprint folder
- **Output**: Generated release notes combining all documentation types

## Sprint Folder Naming Convention

Use the following naming pattern for sprint folders:
- `sprint-YYYY-MM` (e.g., `sprint-2024-01`)
- `sprint-YYYY-QX` (e.g., `sprint-2024-Q1`)
- `sprint-[custom-name]` (e.g., `sprint-mobile-app-v2`)

## Documentation Guidelines

### File Naming
- Use descriptive, kebab-case filenames
- Include version numbers when applicable
- Add dates for time-sensitive documents

### Content Structure
- Start each document with a clear title and date
- Include a summary or overview section
- Use consistent formatting across all documents
- Include relevant links to Jira tickets, designs, or other resources

### Examples
```
sprint-2024-01/
├── PRDs/
│   ├── user-authentication-v2.md
│   ├── payment-integration-requirements.md
│   └── mobile-app-navigation-spec.md
├── Tech-docs/
│   ├── api-changes-v2.1.md
│   ├── database-migration-guide.md
│   └── microservices-architecture.md
└── Docs/
    ├── deployment-checklist.md
    ├── user-training-guide.md
    └── configuration-changes.md
```

## Integration with Jira

The repository is designed to work seamlessly with your Jira workflow:

1. **Sprint Planning**: Create sprint folder and add initial documentation
2. **Development**: Update documentation as features are developed
3. **Sprint Review**: Ensure all documentation is complete and accurate
4. **Sprint Closure**: Bot automatically processes documentation when Jira tickets are closed
5. **Release Notes**: Generated release notes are published automatically

## Best Practices

### For Product Managers
- Keep PRDs up-to-date throughout the sprint
- Include clear acceptance criteria
- Document any scope changes or decisions

### For Developers
- Update technical documentation as you code
- Include code examples and API specifications
- Document any breaking changes or migrations

### For DevOps/Infrastructure
- Document deployment procedures
- Include configuration changes
- Note any infrastructure updates

## Getting Started

1. **Clone the repository**:
   ```bash
   git clone [repository-url]
   cd pre-release-notes-docs
   ```

2. **Create a new sprint folder**:
   ```bash
   mkdir sprint-2024-01
   mkdir sprint-2024-01/PRDs
   mkdir sprint-2024-01/Tech-docs
   mkdir sprint-2024-01/Docs
   ```

3. **Add your documentation** following the guidelines above

4. **Commit and push** your changes:
   ```bash
   git add .
   git commit -m "Add documentation for sprint-2024-01"
   git push origin main
   ```

## Support

For questions about this repository or the documentation process, please contact the development team or create an issue in the repository.

---

**Note**: This repository is part of Capillary's automated release notes generation system. Ensure all documentation is complete and accurate before sprint closure to generate comprehensive release notes.
