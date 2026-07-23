# key_result_areas

## Table Purpose

Defines strategic key result areas (KRAs) within each programme that organize related activities and outcomes.

**Common Use Cases:** Strategic alignment, activity organization, hierarchical performance tracking

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `kra_id` | Integer (11-bit) | ✗ | Stores kra id | Foreign key reference to related record |
| `programme_id` | Integer (11-bit) | ✗ | Stores programme id | Foreign key reference to related record |
| `kra_name` | String (max 255 characters) | ✗ | Stores kra name | Reference value |
| `kra_description` | Long Text | ✓ | Stores kra description | Reference value |
| `linked_outcome` | String (max 200 characters) | ✓ | Stores linked outcome | Reference value |
| `target_completion_date` | Date | ✓ | Stores target completion date | Temporal tracking for audit and analysis |
| `is_active` | Integer (1-bit) | ✓ | Stores is active | Status flag for filtering and workflow control |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### kra_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores kra id. Use this to establish relationships with other tables. 

### programme_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores programme id. Use this to establish relationships with other tables. 

### kra_name

- **Type:** String (max 255 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores kra name. 

### kra_description

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores kra description. 

### linked_outcome

- **Type:** String (max 200 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores linked outcome. 

### target_completion_date

- **Type:** Date
- **Nullability:** Nullable

**Usage Notes:**
This column stores target completion date. Use this column for temporal queries, sorting, and audit trails. 

### is_active

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is active. Use boolean logic to include/exclude records in queries and business logic. 

### created_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores created at. Use this column for temporal queries, sorting, and audit trails. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

