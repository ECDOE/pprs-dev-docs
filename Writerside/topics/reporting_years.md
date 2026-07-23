# reporting_years

## Table Purpose

Defines annual reporting periods that contain multiple quarters.

**Common Use Cases:** Annual planning cycles, long-term performance tracking, multi-year comparisons

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `year_id` | Integer (11-bit) | ✗ | Stores year id | Foreign key reference to related record |
| `year_name` | String (max 20 characters) | ✗ | Stores year name | Reference value |
| `start_date` | Date | ✗ | Stores start date | Temporal tracking for audit and analysis |
| `end_date` | Date | ✗ | Stores end date | Temporal tracking for audit and analysis |
| `submission_deadline` | Date | ✓ | Stores submission deadline | Reference value |
| `is_current` | Integer (1-bit) | ✓ | Stores is current | Status flag for filtering and workflow control |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### year_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores year id. Use this to establish relationships with other tables. 

### year_name

- **Type:** String (max 20 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores year name. 

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

### submission_deadline

- **Type:** Date
- **Nullability:** Nullable

**Usage Notes:**
This column stores submission deadline. 

### is_current

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is current. Use boolean logic to include/exclude records in queries and business logic. 

### created_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores created at. Use this column for temporal queries, sorting, and audit trails. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

