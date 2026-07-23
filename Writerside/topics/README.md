# Database Documentation Package

## Contents

This package contains complete, professional-grade documentation for the **ec_data** database schema.

### Files Included

- **INDEX.md** — Master reference guide with database overview, naming conventions, and best practices
- **31 Table Documentation Files** — Individual markdown files for each database table:
  - User & Authentication (8 files)
  - Programme & Strategy (3 files)
  - Indicators & Targets (3 files)
  - Data Capture & Workflow (3 files)
  - Reporting & Readiness (4 files)
  - Deadline Management (2 files)
  - File & Data Management (4 files)
  - Risk Management (1 file)
  - Performance Optimization (2 files)

## Documentation Format

Each table documentation includes:

1. **Table Purpose** — Strategic intent and primary function
2. **Column Reference Table** — Quick-lookup with:
   - Column name (exact as in schema)
   - Data type (human-readable)
   - Nullability indicator
   - Column meaning
   - Usage pattern
3. **Detailed Column Descriptions** — Per-column specifications with:
   - Type and nullability
   - Primary/auto-increment status
   - Description from schema comments
   - Usage guidance
4. **Relationships** — Cross-table reference information

## How to Use

### For Database Designers
1. Start with **INDEX.md** for schema overview
2. Review specific table files for structure details
3. Check naming conventions and best practices
4. Understand type system and field patterns

### For Application Developers
1. Review **INDEX.md** for data model overview
2. Look up relevant tables (grouped by domain)
3. Check column usage patterns
4. Understand workflow through capture/approval tables

### For DBAs and Analysts
1. Use **INDEX.md** common query patterns
2. Review individual table files for foreign key relationships
3. Check audit and logging tables for compliance queries
4. Leverage materialized view documentation for optimization

## Key Features

✓ **Exact Column Names** — All names preserved from SQL schema  
✓ **Comprehensive Coverage** — Every column documented  
✓ **Professional Format** — Organized markdown structure  
✓ **Type Reference** — Clear type system documentation  
✓ **Best Practices** — Database optimization guidance  
✓ **Audit Trail** — Security and compliance guidance  
✓ **Cross-Table Navigation** — Relationship documentation  

## Schema Highlights

**Total Tables:** 31  
**Total Columns:** 400+  
**Type System:** INT, BIGINT, VARCHAR, TEXT, DECIMAL, DATE, DATETIME, TIMESTAMP, ENUM, TINYINT  
**Storage:** InnoDB with UTF-8 (utf8mb4)  
**Database:** MariaDB 10.4.32

## Organizational Structure

The schema is organized around these core domains:

```
USERS & SECURITY
├── users (accounts, credentials, profiles)
├── user_roles (permissions framework)
├── user_programmes (access assignments)
├── user_sessions (session management)
├── user_activity_log (audit trail)
└── password/login tables

PROGRAMMES & STRATEGY
├── programmes (strategic programmes)
├── key_result_areas (KRA organization)
└── kra_activities (deliverables)

INDICATORS & TARGETS
├── outcome_indicators (performance metrics)
├── indicator_technical_details (definitions)
└── indicator_annual_targets (annual goals)

DATA CAPTURE & APPROVAL
├── indicator_captures (quarterly submissions)
├── indicator_capture_history (audit trail)
└── strategic_review_drafts (review notes)

REPORTING
├── reporting_quarters (temporal periods)
├── reporting_years (annual cycles)
├── programme_overview_reports (narratives)
└── pm_report_readiness (submission status)

WORKFLOW & NOTIFICATIONS
├── deadline_configurations (deadline settings)
├── deadline_extensions (extension tracking)
└── notifications (user alerts)

FILE MANAGEMENT
├── uploaded_files (attachments)
└── file_access_log (usage audit)

COMPLIANCE & MONITORING
├── data_access_log (data access audit)
├── system_settings (configuration)
└── risks (programme risks)

PERFORMANCE
├── dashboard_kpi_cache (KPI metrics)
└── mat_hod_dashboard (executive view)
```

## Navigation Guide

| Looking For | Start Here |
|-------------|-----------|
| Database overview | INDEX.md |
| Specific table details | `{table_name}.md` |
| Column types reference | INDEX.md → Type System Reference |
| Query patterns | INDEX.md → Common Query Patterns |
| Best practices | INDEX.md → Best Practices |
| Naming conventions | INDEX.md → Naming Conventions |
| Approval workflows | indicator_captures.md |
| User access control | users.md + user_roles.md |
| Audit trail | user_activity_log.md |
| Reporting structure | reporting_quarters.md + reporting_years.md |

## Quality Standards

This documentation adheres to:

✓ **Accuracy** — Auto-generated from SQL schema  
✓ **Completeness** — 100% table and column coverage  
✓ **Consistency** — Uniform formatting and terminology  
✓ **Clarity** — Non-technical descriptions for all columns  
✓ **Usability** — Multiple entry points and cross-references  
✓ **Best Practices** — Database design and optimization guidance  

## Updates and Maintenance

This documentation was generated from the SQL schema. To keep it current:

1. Regenerate when schema changes occur
2. Review new or modified columns
3. Update INDEX.md with any structural changes
4. Version control for tracking changes

---

**Database:** ec_data  
**Generated:** July 2026  
**Total Pages:** 32 markdown files  
**Total Coverage:** 31 tables, 400+ columns

Start with **INDEX.md** for a complete overview.
