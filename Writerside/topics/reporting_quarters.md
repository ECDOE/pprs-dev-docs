# reporting_quarters

## Table Purpose

Defines reporting periods on a quarterly basis within the financial year.

**Common Use Cases:** Temporal reporting boundaries, deadline management, submission scheduling

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `quarter_id` | Integer (11-bit) | ✗ | Stores quarter id | Foreign key reference to related record |
| `year_id` | Integer (11-bit) | ✗ | Stores year id | Foreign key reference to related record |
| `quarter_number` | Integer (11-bit) | ✗ | Stores quarter number | Reference value |
| `quarter_name` | String (max 20 characters) | ✗ | Stores quarter name | Reference value |
| `start_date` | Date | ✗ | Stores start date | Temporal tracking for audit and analysis |
| `end_date` | Date | ✗ | Stores end date | Temporal tracking for audit and analysis |
| `is_current` | Integer (1-bit) | ✓ | Stores is current | Status flag for filtering and workflow control |
| `is_locked` | Integer (1-bit) | ✓ | Stores is locked | Status flag for filtering and workflow control |

## Column Descriptions and Usage

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

### quarter_number

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores quarter number. 

### quarter_name

- **Type:** String (max 20 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores quarter name. 

### start_date

- **Type:** Date
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores start date. Use this column for temporal queries, sorting, and audit trails. 

### end_date

- **Type:** Date
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores end date. Use this column for temporal queries, sorting, and audit trails. 

### is_current

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is current. Use boolean logic to include/exclude records in queries and business logic. 

### is_locked

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is locked. Use boolean logic to include/exclude records in queries and business logic. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

