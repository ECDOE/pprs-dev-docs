# user_sessions

## Table Purpose

Tracks active user sessions for security, timeout management, and concurrent access control.

**Common Use Cases:** Session management, timeout enforcement, single sign-on tracking

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `session_id` | Integer (11-bit) | ✗ | Stores session id | Foreign key reference to related record |
| `user_id` | Integer (11-bit) | ✗ | Stores user id | Foreign key reference to related record |
| `session_token` | String (max 255 characters) | ✗ | Stores session token | Reference value |
| `ip_address` | String (max 45 characters) | ✗ | Stores ip address | Reference value |
| `user_agent` | Long Text | ✓ | Stores user agent | Reference value |
| `device_info` | String (max 255 characters) | ✓ | Stores device info | Reference value |
| `browser` | String (max 100 characters) | ✓ | Stores browser | Reference value |
| `operating_system` | String (max 100 characters) | ✓ | Stores operating system | Reference value |
| `login_time` | DateTime | ✗ | Stores login time | Reference value |
| `logout_time` | DateTime | ✓ | Stores logout time | Reference value |
| `logout_type` | Enumeration: user, system, timeout, forced | ✓ | Stores logout type | Reference value |
| `session_duration_seconds` | Integer (11-bit) | ✓ | Stores session duration seconds | Reference value |
| `is_active` | Integer (1-bit) | ✓ | Stores is active | Status flag for filtering and workflow control |
| `last_activity` | DateTime | ✗ | Stores last activity | Reference value |

## Column Descriptions and Usage

### session_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores session id. Use this to establish relationships with other tables. 

### user_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores user id. Use this to establish relationships with other tables. 

### session_token

- **Type:** String (max 255 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores session token. 

### ip_address

- **Type:** String (max 45 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores ip address. 

### user_agent

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores user agent. 

### device_info

- **Type:** String (max 255 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores device info. 

### browser

- **Type:** String (max 100 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores browser. 

### operating_system

- **Type:** String (max 100 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores operating system. 

### login_time

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores login time. 

### logout_time

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores logout time. 

### logout_type

- **Type:** Enumeration: user, system, timeout, forced
- **Nullability:** Nullable

**Usage Notes:**
This column stores logout type. 

### session_duration_seconds

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores session duration seconds. 

### is_active

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is active. Use boolean logic to include/exclude records in queries and business logic. 

### last_activity

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores last activity. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

