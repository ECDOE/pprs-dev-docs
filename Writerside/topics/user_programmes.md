# user_programmes

## Table Purpose

Establishes many-to-many relationships between users and programmes, allowing users to be assigned to multiple programmes.

**Common Use Cases:** Multi-programme access management, programme-specific user filtering

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `user_programme_id` | Integer (11-bit) | ✗ | Stores user programme id | Foreign key reference to related record |
| `user_id` | Integer (11-bit) | ✗ | Stores user id | Foreign key reference to related record |
| `programme_id` | Integer (11-bit) | ✗ | Stores programme id | Foreign key reference to related record |
| `assigned_date` | DateTime | ✗ | Stores assigned date | Temporal tracking for audit and analysis |
| `is_primary` | Integer (1-bit) | ✓ | Stores is primary | Reference value |

## Column Descriptions and Usage

### user_programme_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores user programme id. Use this to establish relationships with other tables. 

### user_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores user id. Use this to establish relationships with other tables. 

### programme_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores programme id. Use this to establish relationships with other tables. 

### assigned_date

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores assigned date. Use this column for temporal queries, sorting, and audit trails. 

### is_primary

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is primary. Use boolean logic to include/exclude records in queries and business logic. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

