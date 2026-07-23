# user_password_history

## Table Purpose

Maintains password change history to enforce password reuse policies and security requirements.

**Common Use Cases:** Password reuse prevention, security policy enforcement

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `history_id` | Integer (11-bit) | ✗ | Stores history id | Foreign key reference to related record |
| `user_id` | Integer (11-bit) | ✗ | Stores user id | Foreign key reference to related record |
| `password` | String (max 255 characters) | ✗ | Stores password | Reference value |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### history_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores history id. Use this to establish relationships with other tables. 

### user_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores user id. Use this to establish relationships with other tables. 

### password

- **Type:** String (max 255 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores password. 

### created_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores created at. Use this column for temporal queries, sorting, and audit trails. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

