# mat_hod_dashboard

## Table Purpose

Materializes approved indicator data for HOD dashboard performance display, optimized for query performance.

**Common Use Cases:** Executive dashboard rendering, performance visualization, quick-access reporting

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `programme_id` | Integer (11-bit) | ✗ | Stores programme id | Foreign key reference to related record |
| `indicator_id` | Integer (11-bit) | ✗ | Stores indicator id | Foreign key reference to related record |
| `quarter_id` | Integer (11-bit) | ✗ | Stores quarter id | Foreign key reference to related record |
| `year_id` | Integer (11-bit) | ✗ | Stores year id | Foreign key reference to related record |
| `actual_value` | Decimal Number | ✓ | Stores actual value | Reference value |
| `planned_value` | Decimal Number | ✓ | Stores planned value | Reference value |
| `quarterly_achievement` | Decimal Number | ✓ | Stores quarterly achievement | Reference value |
| `annual_target_value` | Decimal Number | ✓ | Stores annual target value | Reference value |
| `cp_status` | Enumeration: pending_cp_review, cp_approved, cp_rejected | ✓ | Stores cp status | Workflow or state tracking |
| `refreshed_at` | DateTime | ✗ | Stores refreshed at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### programme_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores programme id. Use this to establish relationships with other tables. 

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

### actual_value

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores actual value. 

### planned_value

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores planned value. 

### quarterly_achievement

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores quarterly achievement. 

### annual_target_value

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores annual target value. 

### cp_status

- **Type:** Enumeration: pending_cp_review, cp_approved, cp_rejected
- **Nullability:** Nullable

**Usage Notes:**
This column stores cp status. Filter records by status to identify items at specific workflow stages. 

### refreshed_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores refreshed at. Use this column for temporal queries, sorting, and audit trails. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

