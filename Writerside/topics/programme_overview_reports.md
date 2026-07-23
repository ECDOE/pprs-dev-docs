# programme_overview_reports

## Table Purpose

Stores quarterly reports submitted by programme managers synthesizing performance, budget, and strategic notes.

**Common Use Cases:** Quarterly reporting, performance synthesis, executive communication

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `report_id` | Integer (11-bit) | ✗ | Stores report id | Foreign key reference to related record |
| `programme_id` | Integer (11-bit) | ✗ | Stores programme id | Foreign key reference to related record |
| `quarter_id` | Integer (11-bit) | ✗ | Stores quarter id | Foreign key reference to related record |
| `year_id` | Integer (11-bit) | ✗ | Stores year id | Foreign key reference to related record |
| `executive_statement` | Long Text | ✓ | Stores executive statement | Workflow or state tracking |
| `programme_budget` | Decimal Number | ✓ | Stores programme budget | Reference value |
| `programme_allocated` | Decimal Number | ✓ | Stores programme allocated | Reference value |
| `programme_expenditure` | Decimal Number | ✓ | Stores programme expenditure | Reference value |
| `budget_comment` | Long Text | ✓ | Stores budget comment | Reference value |
| `nsoi_progress_notes` | Long Text | ✓ | Stores nsoi progress notes | Reference value |
| `wayforward_strategy` | Long Text | ✓ | Stores wayforward strategy | Reference value |
| `status` | Enumeration: draft, submitted, approved, rejected, pending_cp_review, cp_approved, cp_rejected | ✓ | Stores status | Workflow or state tracking |
| `created_by` | Integer (11-bit) | ✗ | Stores created by | Reference value |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |
| `submitted_at` | DateTime | ✓ | Stores submitted at | Temporal tracking for audit and analysis |
| `approved_by` | Integer (11-bit) | ✓ | Stores approved by | Reference value |
| `approved_at` | DateTime | ✓ | Stores approved at | Temporal tracking for audit and analysis |
| `updated_at` | DateTime | ✗ | Stores updated at | Temporal tracking for audit and analysis |
| `cp_reviewed_by` | Integer (11-bit) | ✓ | Stores cp reviewed by | Reference value |
| `cp_reviewed_at` | DateTime | ✓ | Stores cp reviewed at | Temporal tracking for audit and analysis |
| `cp_rejection_reason` | Long Text | ✓ | Stores cp rejection reason | Reference value |
| `cp_status` | Enumeration: pending_cp_review, cp_approved, cp_rejected | ✓ | Stores cp status | Workflow or state tracking |

## Column Descriptions and Usage

### report_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores report id. Use this to establish relationships with other tables. 

### programme_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores programme id. Use this to establish relationships with other tables. 

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

### executive_statement

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores executive statement. 

### programme_budget

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores programme budget. 

### programme_allocated

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores programme allocated. 

### programme_expenditure

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores programme expenditure. 

### budget_comment

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores budget comment. 

### nsoi_progress_notes

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores nsoi progress notes. 

### wayforward_strategy

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores wayforward strategy. 

### status

- **Type:** Enumeration: draft, submitted, approved, rejected, pending_cp_review, cp_approved, cp_rejected
- **Nullability:** Nullable

**Usage Notes:**
This column stores status. Filter records by status to identify items at specific workflow stages. 

### created_by

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores created by. 

### created_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores created at. Use this column for temporal queries, sorting, and audit trails. 

### submitted_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores submitted at. Use this column for temporal queries, sorting, and audit trails. 

### approved_by

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores approved by. 

### approved_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores approved at. Use this column for temporal queries, sorting, and audit trails. 

### updated_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores updated at. Use this column for temporal queries, sorting, and audit trails. 

### cp_reviewed_by

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores cp reviewed by. 

### cp_reviewed_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores cp reviewed at. Use this column for temporal queries, sorting, and audit trails. 

### cp_rejection_reason

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores cp rejection reason. 

### cp_status

- **Type:** Enumeration: pending_cp_review, cp_approved, cp_rejected
- **Nullability:** Nullable

**Usage Notes:**
This column stores cp status. Filter records by status to identify items at specific workflow stages. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

