# Pre-Release Notes Documentation Repository

## Overview

This repository serves as a centralized documentation hub for Capillary's sprint-based development process. It contains Product Requirements Documents (PRDs), Technical Documentation, and general documentation that will be automatically processed to generate release notes when Jira tickets are closed.

## Quarterly Organization

The repository is organized by quarters to provide better structure and easier navigation:

- **2025_JFM**: Q1 (January, February, March)
- **2025_AMJ**: Q2 (April, May, June)  
- **2025_JAS**: Q3 (July, August, September)
- **2025_OND**: Q4 (October, November, December)

Each quarter contains monthly folders, and each month typically contains 2 sprints with their respective CAP tickets and documentation.

## Repository Structure

```
pre-release-notes-docs/
├── 2025_JFM/               # Q1: January, February, March
│   ├── January/
│   │   ├── Sprint_XX_01012025/
│   │   │   ├── CAP-123/
│   │   │   │   ├── Doc/           # General Documentation
│   │   │   │   ├── PRD/           # Product Requirements Documents
│   │   │   │   └── TechDoc/       # Technical Documentation
│   │   │   └── CAP-456/
│   │   │       ├── Doc/
│   │   │       ├── PRD/
│   │   │       └── TechDoc/
│   │   └── Sprint_XX_15012025/
│   │       └── CAP-789/
│   │           ├── Doc/
│   │           ├── PRD/
│   │           └── TechDoc/
│   ├── February/
│   │   ├── Sprint_XX_01022025/
│   │   └── Sprint_XX_15022025/
│   └── March/
│       ├── Sprint_XX_01032025/
│       └── Sprint_XX_15032025/
├── 2025_AMJ/               # Q2: April, May, June
│   ├── April/
│   ├── May/
│   └── June/
├── 2025_JAS/               # Q3: July, August, September
│   ├── July/
│   │   ├── Sprint_55_16072025/
│   │   └── Sprint_56_02082025/
│   ├── August/
│   │   ├── Sprint_XX_01082025/
│   │   └── Sprint_XX_15082025/
│   └── September/
│       ├── Sprint_55/
│       ├── Sprint_58/
│       └── Sprint_59/
├── 2025_OND/               # Q4: October, November, December
│   ├── October/
│   ├── November/
│   └── December/
└── README.md               # This file
```

## Workflow

### 1. Sprint Documentation Phase
- **Timeline**: During each sprint
- **Action**: Team members populate the sprint-specific folder with documentation
- **Structure**: Create a folder named after the sprint (e.g., `Sprint_55_16072025`) within the appropriate month folder, with CAP ticket folders containing three subfolders

### 2. Documentation Types

#### PRDs (Product Requirements Documents)
- **Location**: `[quarter]/[month]/[sprint-name]/[CAP-ticket]/PRD/`
- **Content**: 
  - Feature specifications
  - User stories
  - Acceptance criteria
  - Business requirements
  - Product decisions

#### TechDoc (Technical Documentation)
- **Location**: `[quarter]/[month]/[sprint-name]/[CAP-ticket]/TechDoc/`
- **Content**:
  - Architecture changes
  - API documentation
  - Database schema changes
  - Technical specifications
  - Code documentation
  - Infrastructure changes

#### Doc (General Documentation)
- **Location**: `[quarter]/[month]/[sprint-name]/[CAP-ticket]/Doc/`
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

## Folder Naming Convention

### Quarterly Folders
Use the following naming pattern for quarterly folders:
- `2025_JFM` (January, February, March)
- `2025_AMJ` (April, May, June)
- `2025_JAS` (July, August, September)
- `2025_OND` (October, November, December)

### Month Folders
- Use full month names: `January`, `February`, `March`, etc.

### Sprint Folders
Use the following naming pattern for sprint folders:
- `Sprint_XX_MMDDYYYY` (e.g., `Sprint_55_16072025`)
- `Sprint_XX_MMDDYYYY` (e.g., `Sprint_56_02082025`)

### CAP Ticket Folders
- Use the format: `CAP-XXXXXX` (e.g., `CAP-145826`, `CAP-154738`)

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
2025_JAS/July/Sprint_55_16072025/
├── CAP-145826/
│   ├── Doc/
│   │   └── API Doc.md
│   ├── PRD/
│   │   └── Update vendor metadata - PRD.md
│   └── TechDoc/
│       └── vendor-metadata-tech-spec.md
├── CAP-154738/
│   ├── Doc/
│   │   └── coupon-validation-docs.md
│   ├── PRD/
│   │   └── validTillDate in coupons.md
│   └── TechDoc/
│       └── tech doc.md
└── CAP-144282/
    ├── Doc/
    │   └── documentation -transaction _number - documentation.md
    ├── PRD/
    │   └── prd - Add the filter for _transactionNumber_ in get all customer coupons v2 API _ Phase 1 for coupon reversal on txn return.md
    └── TechDoc/
        └── transaction_numbers.pdf
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

2. **Create a new sprint folder structure**:
   ```bash
   # Create quarterly folder (if not exists)
   mkdir -p 2025_JAS/July
   
   # Create sprint folder
   mkdir 2025_JAS/July/Sprint_55_16072025
   
   # Create CAP ticket folder
   mkdir 2025_JAS/July/Sprint_55_16072025/CAP-123456
   
   # Create documentation subfolders
   mkdir 2025_JAS/July/Sprint_55_16072025/CAP-123456/Doc
   mkdir 2025_JAS/July/Sprint_55_16072025/CAP-123456/PRD
   mkdir 2025_JAS/July/Sprint_55_16072025/CAP-123456/TechDoc
   ```

3. **Add your documentation** following the guidelines above

4. **Commit and push** your changes:
   ```bash
   git add .
   git commit -m "Add documentation for Sprint_55_16072025 - CAP-123456"
   git push origin main
   ```

## Support

For questions about this repository or the documentation process, please contact the development team or create an issue in the repository.

---

**Note**: This repository is part of Capillary's automated release notes generation system. Ensure all documentation is complete and accurate before sprint closure to generate comprehensive release notes.
