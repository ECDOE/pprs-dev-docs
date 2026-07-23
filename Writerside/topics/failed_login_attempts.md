# failed_login_attempts

## Table Purpose

Tracks failed login attempts to implement account lockout mechanisms and prevent brute-force attacks.

**Common Use Cases:** Security monitoring, account lockout implementation, failed access investigation

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `attempt_id` | Integer (11-bit) | ✗ | Stores attempt id | Foreign key reference to related record |
| `username` | String (max 50 characters) | ✓ | Stores username | Reference value |
| `email` | String (max 100 characters) | ✓ | Stores email | Reference value |
| `ip_address` | String (max 45 characters) | ✗ | Stores ip address | Reference value |
| `attempt_timestamp` | DateTime | ✗ | Stores attempt timestamp | Reference value |

## Column Descriptions and Usage

### attempt_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores attempt id. Use this to establish relationships with other tables. 

### username

- **Type:** String (max 50 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores username. 

### email

- **Type:** String (max 100 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores email. 

### ip_address

- **Type:** String (max 45 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores ip address. 

### attempt_timestamp

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores attempt timestamp. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

