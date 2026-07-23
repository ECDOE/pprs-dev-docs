# indicator_captures

## Table Purpose

Records actual quarterly data submissions for indicators, including approval workflows and status tracking.

**Common Use Cases:** Quarterly data entry, multi-stage approval process, variance calculation, performance reporting

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `capture_id` | Integer (11-bit) | ✗ | Stores capture id | Foreign key reference to related record |
| `indicator_id` | Integer (11-bit) | ✗ | Stores indicator id | Foreign key reference to related record |
| `quarter_id` | Integer (11-bit) | ✗ | Stores quarter id | Foreign key reference to related record |
| `year_id` | Integer (11-bit) | ✗ | Stores year id | Foreign key reference to related record |
| `planned_value` | Decimal Number | ✓ | Stores planned value | Reference value |
| `actual_value` | Decimal Number | ✓ | Stores actual value | Reference value |
| `quarterly_achievement` | Decimal Number | ✓ | Stores quarterly achievement | Reference value |
| `actual_expenditure` | Decimal Number | ✓ | Actual expenditure incurred for this indicator during this quarter | Reference value |
| `key_activities` | Long Text | ✓ | Stores key activities | Reference value |
| `reason_for_deviation` | Long Text | ✓ | Stores reason for deviation | Reference value |
| `challenges` | Long Text | ✓ | Stores challenges | Reference value |
| `impact` | Long Text | ✓ | Stores impact | Reference value |
| `corrective_measures` | Long Text | ✓ | Stores corrective measures | Reference value |
| `portfolio_of_evidence` | Long Text | ✓ | Stores portfolio of evidence | Reference value |
| `evidence_files` | Long Text | ✓ | Stores evidence files | Reference value |
| `status` | Enumeration: draft, submitted, approved, rejected | ✓ | Stores status | Workflow or state tracking |
| `rejection_reason` | Long Text | ✓ | Stores rejection reason | Reference value |
| `rejection_date` | DateTime | ✓ | Stores rejection date | Temporal tracking for audit and analysis |
| `captured_by` | Integer (11-bit) | ✗ | Stores captured by | Reference value |
| `captured_at` | DateTime | ✗ | Stores captured at | Temporal tracking for audit and analysis |
| `submitted_at` | DateTime | ✓ | Stores submitted at | Temporal tracking for audit and analysis |
| `reviewed_by` | Integer (11-bit) | ✓ | Stores reviewed by | Reference value |
| `reviewed_at` | DateTime | ✓ | Stores reviewed at | Temporal tracking for audit and analysis |
| `approved_by` | Integer (11-bit) | ✓ | Stores approved by | Reference value |
| `approved_at` | DateTime | ✓ | Stores approved at | Temporal tracking for audit and analysis |
| `updated_at` | DateTime | ✗ | Stores updated at | Temporal tracking for audit and analysis |
| `version_number` | Integer (11-bit) | ✓ | Stores version number | Reference value |
| `cp_reviewed_by` | Integer (11-bit) | ✓ | Corporate Planning reviewer | Reference value |
| `cp_reviewed_at` | DateTime | ✓ | Stores cp reviewed at | Temporal tracking for audit and analysis |
| `cp_rejection_reason` | Long Text | ✓ | Stores cp rejection reason | Reference value |
| `cp_comments` | Long Text | ✓ | Corporate Planning reviewer comments | Reference value |
| `poe_verified` | Integer (1-bit) | ✓ | Portfolio of Evidence verified flag | Reference value |
| `cp_status` | Enumeration: pending_cp_review, cp_approved, cp_rejected | ✓ | Status after PM approval | Workflow or state tracking |

## Column Descriptions and Usage

### capture_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores capture id. Use this to establish relationships with other tables. 

### indicator_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores indicator id. Use this to establish relationships with other tables. 

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

### planned_value

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores planned value. 

### actual_value

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores actual value. 

### quarterly_achievement

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores quarterly achievement. 

### actual_expenditure

- **Type:** Decimal Number
- **Nullability:** Nullable
- **Description:** Actual expenditure incurred for this indicator during this quarter

**Usage Notes:**
This column stores actual expenditure. 

### key_activities

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores key activities. 

### reason_for_deviation

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores reason for deviation. 

### challenges

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores challenges. 

### impact

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores impact. 

### corrective_measures

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores corrective measures. 

### portfolio_of_evidence

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores portfolio of evidence. 

### evidence_files

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores evidence files. 

### status

- **Type:** Enumeration: draft, submitted, approved, rejected
- **Nullability:** Nullable

**Usage Notes:**
This column stores status. Filter records by status to identify items at specific workflow stages. 

### rejection_reason

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores rejection reason. 

### rejection_date

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores rejection date. Use this column for temporal queries, sorting, and audit trails. 

### captured_by

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores captured by. 

### captured_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores captured at. Use this column for temporal queries, sorting, and audit trails. 

### submitted_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores submitted at. Use this column for temporal queries, sorting, and audit trails. 

### reviewed_by

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores reviewed by. 

### reviewed_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores reviewed at. Use this column for temporal queries, sorting, and audit trails. 

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

### version_number

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores version number. 

### cp_reviewed_by

- **Type:** Integer (11-bit)
- **Nullability:** Nullable
- **Description:** Corporate Planning reviewer

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

### cp_comments

- **Type:** Long Text
- **Nullability:** Nullable
- **Description:** Corporate Planning reviewer comments

**Usage Notes:**
This column stores cp comments. 

### poe_verified

- **Type:** Integer (1-bit)
- **Nullability:** Nullable
- **Description:** Portfolio of Evidence verified flag

**Usage Notes:**
This column stores poe verified. 

### cp_status

- **Type:** Enumeration: pending_cp_review, cp_approved, cp_rejected
- **Nullability:** Nullable
- **Description:** Status after PM approval

**Usage Notes:**
This column stores cp status. Filter records by status to identify items at specific workflow stages. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

