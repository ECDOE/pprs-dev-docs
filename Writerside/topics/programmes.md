# programmes

## Table Purpose

Represents strategic programmes that contain outcome indicators and are managed by programme managers.

**Common Use Cases:** Programme hierarchies, indicator organization, budget allocation, reporting structure

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `programme_id` | Integer (11-bit) | ✗ | Stores programme id | Foreign key reference to related record |
| `programme_code` | String (max 20 characters) | ✗ | Stores programme code | Reference value |
| `programme_name` | String (max 200 characters) | ✗ | Stores programme name | Reference value |
| `programme_description` | Long Text | ✓ | Stores programme description | Reference value |
| `programme_manager_id` | Integer (11-bit) | ✓ | Stores programme manager id | Foreign key reference to related record |
| `is_active` | Integer (1-bit) | ✓ | Stores is active | Status flag for filtering and workflow control |
| `display_order` | Integer (11-bit) | ✓ | Stores display order | Reference value |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |
| `updated_at` | DateTime | ✗ | Stores updated at | Temporal tracking for audit and analysis |
| `user_id` | Integer (11-bit) | ✓ | Stores user id | Foreign key reference to related record |

## Column Descriptions and Usage

### programme_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores programme id. Use this to establish relationships with other tables. 

### programme_code

- **Type:** String (max 20 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores programme code. 

### programme_name

- **Type:** String (max 200 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores programme name. 

### programme_description

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores programme description. 

### programme_manager_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores programme manager id. Use this to establish relationships with other tables. 

### is_active

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is active. Use boolean logic to include/exclude records in queries and business logic. 

### display_order

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores display order. 

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

### user_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores user id. Use this to establish relationships with other tables. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

