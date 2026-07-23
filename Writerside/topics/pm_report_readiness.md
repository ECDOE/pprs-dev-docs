# pm_report_readiness

## Table Purpose

Calculates and caches readiness status for programmes to submit quarterly reports.

**Common Use Cases:** Report submission workflow, readiness dashboard, budget-indicator alignment checks

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `readiness_id` | Integer (11-bit) | ✗ | Stores readiness id | Foreign key reference to related record |
| `programme_id` | Integer (11-bit) | ✗ | Stores programme id | Foreign key reference to related record |
| `quarter_id` | Integer (11-bit) | ✗ | Stores quarter id | Foreign key reference to related record |
| `year_id` | Integer (11-bit) | ✗ | Stores year id | Foreign key reference to related record |
| `total_indicators` | Integer (11-bit) | ✓ | Stores total indicators | Reference value |
| `captured_indicators` | Integer (11-bit) | ✓ | Stores captured indicators | Reference value |
| `approved_indicators` | Integer (11-bit) | ✓ | Stores approved indicators | Reference value |
| `is_ready_to_submit` | Integer (1-bit) | ✓ | Stores is ready to submit | Reference value |
| `last_calculated` | DateTime | ✗ | Stores last calculated | Reference value |
| `total_allocated_budget` | Decimal Number | ✓ | Stores total allocated budget | Reference value |
| `total_actual_expenditure` | Decimal Number | ✓ | Stores total actual expenditure | Reference value |
| `budget_variance_pct` | Decimal Number | ✓ | Stores budget variance pct | Reference value |
| `budget_status` | String (max 50 characters) | ✓ | Stores budget status | Workflow or state tracking |
| `budget_ready` | Integer (1-bit) | ✓ | 1 = all approved captures have expenditure captured | Reference value |

## Column Descriptions and Usage

### readiness_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores readiness id. Use this to establish relationships with other tables. 

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

### total_indicators

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores total indicators. 

### captured_indicators

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores captured indicators. 

### approved_indicators

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores approved indicators. 

### is_ready_to_submit

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is ready to submit. Use boolean logic to include/exclude records in queries and business logic. 

### last_calculated

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores last calculated. 

### total_allocated_budget

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores total allocated budget. 

### total_actual_expenditure

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores total actual expenditure. 

### budget_variance_pct

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores budget variance pct. 

### budget_status

- **Type:** String (max 50 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores budget status. Filter records by status to identify items at specific workflow stages. 

### budget_ready

- **Type:** Integer (1-bit)
- **Nullability:** Nullable
- **Description:** 1 = all approved captures have expenditure captured

**Usage Notes:**
This column stores budget ready. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

