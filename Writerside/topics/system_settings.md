# system_settings

## Table Purpose

Provides centralized configuration storage for system behavior, security policies, and operational parameters.

**Common Use Cases:** Feature toggles, deadline configuration, password policy management, file upload limits

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `setting_id` | Integer (11-bit) | ✗ | Stores setting id | Foreign key reference to related record |
| `setting_key` | String (max 100 characters) | ✗ | Stores setting key | Reference value |
| `setting_value` | Long Text | ✓ | Stores setting value | Reference value |
| `setting_type` | Enumeration: boolean, string, number, date | ✓ | Stores setting type | Reference value |
| `description` | Long Text | ✓ | Stores description | Reference value |
| `is_public` | Integer (1-bit) | ✓ | Stores is public | Reference value |
| `updated_by` | Integer (11-bit) | ✓ | Stores updated by | Reference value |
| `updated_at` | DateTime | ✗ | Stores updated at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### setting_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores setting id. Use this to establish relationships with other tables. 

### setting_key

- **Type:** String (max 100 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores setting key. 

### setting_value

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores setting value. 

### setting_type

- **Type:** Enumeration: boolean, string, number, date
- **Nullability:** Nullable

**Usage Notes:**
This column stores setting type. 

### description

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores description. 

### is_public

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is public. Use boolean logic to include/exclude records in queries and business logic. 

### updated_by

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores updated by. 

### updated_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores updated at. Use this column for temporal queries, sorting, and audit trails. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

