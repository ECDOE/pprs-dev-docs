# indicator_annual_targets

## Table Purpose

Stores annual performance targets for each indicator, setting baseline expectations for quarterly measurement.

**Common Use Cases:** Target setting, variance analysis, annual performance reviews

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `target_id` | Integer (11-bit) | ✗ | Stores target id | Foreign key reference to related record |
| `indicator_id` | Integer (11-bit) | ✗ | Stores indicator id | Foreign key reference to related record |
| `year_id` | Integer (11-bit) | ✗ | Stores year id | Foreign key reference to related record |
| `annual_target_value` | Decimal Number | ✗ | Stores annual target value | Reference value |
| `q1_target` | Decimal Number | ✓ | Stores q1 target | Reference value |
| `q2_target` | Decimal Number | ✓ | Stores q2 target | Reference value |
| `q3_target` | Decimal Number | ✓ | Stores q3 target | Reference value |
| `q4_target` | Decimal Number | ✓ | Stores q4 target | Reference value |
| `allocated_budget` | Decimal Number | ✓ | Budget allocated at the start of the financial year (planning figure) | Reference value |
| `actual_budget` | Decimal Number | ✓ | Confirmed budget. Auto-copied from allocated_budget when No is pressed. Overwritten by user entry when Yes is pressed. Never null once allocated_budget is set. | Reference value |
| `budget_changed` | Integer (1-bit) | ✗ | 0 = No pressed (actual_budget = allocated_budget). 1 = Yes pressed (budget changed). | Reference value |
| `budget_change_reason` | Long Text | ✓ | Reason entered by user when budget_changed = 1. NULL when budget_changed = 0. | Reference value |
| `key_activities` | Long Text | ✓ | Stores key activities | Reference value |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |
| `updated_at` | DateTime | ✗ | Stores updated at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### target_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores target id. Use this to establish relationships with other tables. 

### indicator_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores indicator id. Use this to establish relationships with other tables. 

### year_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores year id. Use this to establish relationships with other tables. 

### annual_target_value

- **Type:** Decimal Number
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores annual target value. 

### q1_target

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores q1 target. 

### q2_target

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores q2 target. 

### q3_target

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores q3 target. 

### q4_target

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores q4 target. 

### allocated_budget

- **Type:** Decimal Number
- **Nullability:** Nullable
- **Description:** Budget allocated at the start of the financial year (planning figure)

**Usage Notes:**
This column stores allocated budget. 

### actual_budget

- **Type:** Decimal Number
- **Nullability:** Nullable
- **Description:** Confirmed budget. Auto-copied from allocated_budget when No is pressed. Overwritten by user entry when Yes is pressed. Never null once allocated_budget is set.

**Usage Notes:**
This column stores actual budget. 

### budget_changed

- **Type:** Integer (1-bit)
- **Nullability:** Required (NOT NULL)
- **Description:** 0 = No pressed (actual_budget = allocated_budget). 1 = Yes pressed (budget changed).

**Usage Notes:**
This column stores budget changed. 

### budget_change_reason

- **Type:** Long Text
- **Nullability:** Nullable
- **Description:** Reason entered by user when budget_changed = 1. NULL when budget_changed = 0.

**Usage Notes:**
This column stores budget change reason. 

### key_activities

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores key activities. 

### created_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores created at. Use this column for temporal queries, sorting, and audit trails. 

### updated_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores updated at. Use this column for temporal queries, sorting, and audit trails. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

