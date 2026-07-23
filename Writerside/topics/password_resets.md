# password_resets

## Table Purpose

Manages password reset tokens and their expiration to enable secure password recovery.

**Common Use Cases:** Password recovery workflow, token validation, reset token expiry enforcement

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `id` | Integer (11-bit) | ✗ | Stores id | Reference value |
| `user_id` | Integer (11-bit) | ✗ | Stores user id | Foreign key reference to related record |
| `token` | String (max 64 characters) | ✗ | Stores token | Reference value |
| `expires_at` | DateTime | ✗ | Stores expires at | Temporal tracking for audit and analysis |
| `used` | Integer (1-bit) | ✗ | Stores used | Reference value |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores id. 

### user_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores user id. Use this to establish relationships with other tables. 

### token

- **Type:** String (max 64 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores token. 

### expires_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores expires at. Use this column for temporal queries, sorting, and audit trails. 

### used

- **Type:** Integer (1-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores used. 

### created_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores created at. Use this column for temporal queries, sorting, and audit trails. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

