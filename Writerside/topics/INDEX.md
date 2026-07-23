# EC Data Database Documentation

**Database:** ec_data  
**Generated:** July 2026  
**Server Version:** MariaDB 10.4.32  
**Character Set:** UTF-8 (utf8mb4)

---

## Overview

This documentation provides complete reference material for the EC Data database schema used in the Eastern Cape Department of Education's indicator management system. The database facilitates quarterly performance reporting, strategic indicator tracking, and multi-level approval workflows.

### Documentation Structure

Each table has been documented in a separate Markdown file containing:

1. **Table Purpose** — Strategic intent and primary function
2. **Column Reference** — Quick-lookup table with type, nullability, and usage
3. **Column Descriptions** — Detailed specifications for each column
4. **Relationships** — Cross-table references and join guidance

---

## Database Tables

### User & Authentication Management

- **[users](users.md)** — User accounts, credentials, and profile information
- **[user_roles](user_roles.md)** — Role definitions and organizational permissions
- **[user_programmes](user_programmes.md)** — Many-to-many assignments of users to programmes
- **[user_sessions](user_sessions.md)** — Active session tracking and timeout management
- **[user_activity_log](user_activity_log.md)** — Comprehensive audit trail of user actions
- **[user_password_history](user_password_history.md)** — Password change history for security policy enforcement
- **[failed_login_attempts](failed_login_attempts.md)** — Failed authentication tracking for lockout mechanisms
- **[password_resets](password_resets.md)** — Password recovery tokens and expiration

### Programme & Strategic Hierarchy

- **[programmes](programmes.md)** — Strategic programmes containing indicators
- **[key_result_areas](key_result_areas.md)** — KRAs organizing programme activities
- **[kra_activities](kra_activities.md)** — Specific deliverables within KRAs

### Indicator Definition & Targets

- **[outcome_indicators](outcome_indicators.md)** — Measurable performance indicators
- **[indicator_technical_details](indicator_technical_details.md)** — Technical specifications and calculation methodology
- **[indicator_annual_targets](indicator_annual_targets.md)** — Annual performance baselines by year

### Indicator Data Capture & Workflow

- **[indicator_captures](indicator_captures.md)** — Quarterly data submissions with multi-stage approval
- **[indicator_capture_history](indicator_capture_history.md)** — Change audit trail for captures
- **[strategic_review_drafts](strategic_review_drafts.md)** — Strategic review notes and evidence verification

### Reporting & Readiness

- **[reporting_quarters](reporting_quarters.md)** — Quarterly reporting periods
- **[reporting_years](reporting_years.md)** — Annual reporting cycles
- **[programme_overview_reports](programme_overview_reports.md)** — Quarterly narrative and performance reports
- **[pm_report_readiness](pm_report_readiness.md)** — Readiness status for report submission

### Deadline & Workflow Management

- **[deadline_configurations](deadline_configurations.md)** — Centralized deadline settings and warning periods
- **[deadline_extensions](deadline_extensions.md)** — Granted deadline extensions with audit trail

### Notifications

- **[notifications](notifications.md)** — System-generated alerts for users

### File Management

- **[uploaded_files](uploaded_files.md)** — Attachment storage with multi-location support
- **[file_access_log](file_access_log.md)** — File download and access audit trail

### Data Access & Security

- **[data_access_log](data_access_log.md)** — Sensitive data access audit trail
- **[system_settings](system_settings.md)** — System configuration and policy parameters

### Risk Management

- **[risks](risks.md)** — Programme-level risks and mitigation tracking

### Performance Optimization (Materialized Views)

- **[dashboard_kpi_cache](dashboard_kpi_cache.md)** — Cached KPI calculations for dashboard performance
- **[mat_hod_dashboard](mat_hod_dashboard.md)** — Materialized HOD dashboard data

---

## Data Model Overview

### Core Workflow

The system implements a multi-stage approval workflow for quarterly indicator data:

1. **Data Capture** — Data capturers submit actual values for indicators
2. **Programme Manager Review** — Managers approve or reject captures
3. **Corporate Planning Review** — CP users perform final approval
4. **Dashboard Publication** — Approved data populates executive dashboards

### Key Relationships

**Programme → Outcome Indicators → Indicator Captures**
- Programmes contain outcome indicators
- Each indicator receives quarterly captures
- Captures track actual vs. target performance

**Users → Roles → Programmes**
- Users have organizational roles
- Users are assigned to manage specific programmes
- Role determines approval authority

**Captures → History → Audit**
- All capture changes are versioned
- Activity logs provide compliance trail
- File attachments serve as evidence

---

## Naming Conventions

### Column Naming Standards

| Pattern | Meaning | Example |
|---------|---------|---------|
| `{table}_id` | Primary key | `user_id`, `programme_id` |
| `{table}_id` | Foreign key | `user_id` (in another table), `programme_id` |
| `is_{status}` | Boolean flag | `is_active`, `is_current`, `is_locked` |
| `{action}_at` | Timestamp | `created_at`, `reviewed_at`, `approved_at` |
| `{action}_by` | User responsible | `created_by`, `reviewed_by`, `approved_by` |
| `{field}_date` | Date value | `start_date`, `end_date`, `identified_date` |
| `{metric}_percentage` | Calculated percentage | `variance_percentage`, `budget_variance_pct` |

### Boolean Representation

- **Stored as:** `tinyint(1)` where 0 = false, 1 = true
- **Examples:** `is_active`, `is_current`, `is_locked`, `is_public`, `is_primary`

---

## Type System Reference

### Numeric Types

| Type | Usage | Size | Range |
|------|-------|------|-------|
| `int(11)` | IDs, counts, small integers | 4 bytes | -2.1B to 2.1B |
| `bigint(20)` | Large sequential IDs (activity logs) | 8 bytes | ±9.2 quintillion |
| `tinyint(1)` | Boolean/flags | 1 byte | 0-255 |
| `decimal(15,2)` | Financial amounts (budget, expenditure) | Variable | 2 decimal places |

### Text Types

| Type | Usage | Max Size |
|------|-------|----------|
| `varchar(20-255)` | Codes, names, short identifiers | Column-specific |
| `text` | Descriptions, comments, narrative | 65KB |
| `longtext` | JSON data, large documents | 4GB |

### Temporal Types

| Type | Usage | Precision | Format |
|------|-------|-----------|--------|
| `date` | Calendar dates (boundaries, deadlines) | Day | YYYY-MM-DD |
| `datetime` | Specific moments (submissions, approvals) | Second | YYYY-MM-DD HH:MM:SS |
| `timestamp` | System tracking (created_at, updated_at) | Second | Auto-managed |

### Enumerated Types

Several columns use `enum()` to restrict values to predefined options:

- **Status values:** draft, submitted, approved, rejected, pending_cp_review, cp_approved, cp_rejected
- **Roles:** System Administrator, Programme Manager, Data Capturer, Corporate Planning, etc.
- **Storage types:** local, google_drive, onedrive, dropbox

---

## Common Query Patterns

### Cross-Table Joins

**Get all captures for a programme in a quarter:**
```
indicator_captures 
  → outcome_indicators (via indicator_id) 
    → programmes (via programme_id)
```

**Get user's assigned programmes:**
```
users 
  → user_programmes (via user_id) 
    → programmes (via programme_id)
```

**Get audit trail for a capture:**
```
indicator_captures 
  → indicator_capture_history (via capture_id) 
    → users (via changed_by)
```

### Nullable Field Handling

- Columns ending in `_by` or `_id` that are nullable indicate optional relationships
- Null values typically represent "not yet assigned" or "not applicable"
- Use `IS NULL` / `IS NOT NULL` filters appropriately

---

## Best Practices

### Data Integrity

1. **Always preserve exact column names** — Don't rename or alias without clear reason
2. **Respect nullability rules** — Don't insert NULL into NOT NULL columns
3. **Use proper date formats** — Store dates as DATE or DATETIME, not strings
4. **Maintain referential integrity** — Foreign key values must exist in parent tables

### Performance Optimization

1. **Use indexed columns** — Filter on `_id`, `status`, `_at` columns first
2. **Avoid SELECT *** — Specify only needed columns
3. **Batch operations** — Use bulk inserts/updates where possible
4. **Leverage materialized views** — Query `dashboard_kpi_cache` and `mat_hod_dashboard` for reports

### Audit & Compliance

1. **Log all changes** — Use activity logging for user actions
2. **Track approvals** — Capture `approved_by` and `approved_at` on decisions
3. **Archive history** — Retain historical records per data retention policies
4. **Validate sources** — Verify file integrity using `file_hash` when provided

---

## Support & Documentation

For detailed information on any specific table:

1. Navigate to the corresponding table's Markdown file (listed above)
2. Review the **Column Reference** table for quick lookups
3. Consult **Column Descriptions and Usage** for detailed specifications
4. Check **Relationships and Cross-Table Usage** for integration patterns

---

## Revision History

| Date | Version | Notes |
|------|---------|-------|
| July 2026 | 1.0 | Initial documentation generated from schema |

---

*This documentation was automatically generated from the SQL schema and should be updated whenever schema changes occur.*
