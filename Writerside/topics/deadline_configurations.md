# deadline_configurations

## Table Purpose

Centralizes deadline management for different phases (capture, review, approval) with role-specific warning periods.

**Common Use Cases:** Deadline enforcement, notification triggers, phase transitions

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `config_id` | Integer (11-bit) | ✗ | Stores config id | Foreign key reference to related record |
| `quarter_id` | Integer (11-bit) | ✗ | Stores quarter id | Foreign key reference to related record |
| `year_id` | Integer (11-bit) | ✗ | Stores year id | Foreign key reference to related record |
| `capturer_submission_deadline` | DateTime | ✗ | Stores capturer submission deadline | Reference value |
| `capturer_warning_days` | Integer (11-bit) | ✓ | Stores capturer warning days | Reference value |
| `capturer_late_submission_allowed` | Integer (1-bit) | ✓ | Stores capturer late submission allowed | Reference value |
| `pm_review_deadline` | DateTime | ✗ | Stores pm review deadline | Reference value |
| `pm_warning_days` | Integer (11-bit) | ✓ | Stores pm warning days | Reference value |
| `pm_auto_escalate` | Integer (1-bit) | ✓ | Stores pm auto escalate | Reference value |
| `cp_review_deadline` | DateTime | ✗ | Stores cp review deadline | Reference value |
| `cp_warning_days` | Integer (11-bit) | ✓ | Stores cp warning days | Reference value |
| `cp_auto_approve` | Integer (1-bit) | ✓ | Stores cp auto approve | Reference value |
| `hod_dashboard_date` | DateTime | ✓ | Stores hod dashboard date | Temporal tracking for audit and analysis |
| `target_setting_open_date` | DateTime | ✓ | Stores target setting open date | Temporal tracking for audit and analysis |
| `target_setting_close_date` | DateTime | ✓ | Stores target setting close date | Temporal tracking for audit and analysis |
| `target_setting_locked` | Integer (1-bit) | ✓ | Stores target setting locked | Reference value |
| `quarter_status` | Enumeration: planning, capture_open, capture_closed, pm_review, cp_review, completed | ✓ | Stores quarter status | Workflow or state tracking |
| `created_by` | Integer (11-bit) | ✓ | Stores created by | Reference value |
| `created_at` | DateTime | ✓ | Stores created at | Temporal tracking for audit and analysis |
| `updated_by` | Integer (11-bit) | ✓ | Stores updated by | Reference value |
| `updated_at` | DateTime | ✓ | Stores updated at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### config_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores config id. Use this to establish relationships with other tables. 

### quarter_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores quarter id. Use this to establish relationships with other tables. 

### year_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores year id. Use this to establish relationships with other tables. 

### capturer_submission_deadline

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores capturer submission deadline. 

### capturer_warning_days

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores capturer warning days. 

### capturer_late_submission_allowed

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores capturer late submission allowed. 

### pm_review_deadline

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores pm review deadline. 

### pm_warning_days

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores pm warning days. 

### pm_auto_escalate

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores pm auto escalate. 

### cp_review_deadline

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores cp review deadline. 

### cp_warning_days

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores cp warning days. 

### cp_auto_approve

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores cp auto approve. 

### hod_dashboard_date

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores hod dashboard date. Use this column for temporal queries, sorting, and audit trails. 

### target_setting_open_date

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores target setting open date. Use this column for temporal queries, sorting, and audit trails. 

### target_setting_close_date

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores target setting close date. Use this column for temporal queries, sorting, and audit trails. 

### target_setting_locked

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores target setting locked. 

### quarter_status

- **Type:** Enumeration: planning, capture_open, capture_closed, pm_review, cp_review, completed
- **Nullability:** Nullable

**Usage Notes:**
This column stores quarter status. Filter records by status to identify items at specific workflow stages. 

### created_by

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores created by. 

### created_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores created at. Use this column for temporal queries, sorting, and audit trails. 

### updated_by

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores updated by. 

### updated_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores updated at. Use this column for temporal queries, sorting, and audit trails. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

