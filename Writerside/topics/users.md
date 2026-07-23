# users

## Table Purpose

Stores user account information, authentication credentials, and access control settings for the indicator management system.

**Common Use Cases:** User login/authentication, role assignment, programme access control, account lockout management

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `user_id` | Integer (11-bit) | ✗ | Stores user id | Foreign key reference to related record |
| `email` | String (max 100 characters) | ✗ | Stores email | Reference value |
| `alternate_email` | String (max 255 characters) | ✓ | Stores alternate email | Reference value |
| `password` | String (max 255 characters) | ✓ | Stores password | Reference value |
| `first_name` | String (max 50 characters) | ✗ | Stores first name | Reference value |
| `last_name` | String (max 50 characters) | ✗ | Stores last name | Reference value |
| `phone` | String (max 20 characters) | ✓ | Stores phone | Reference value |
| `role_id` | Integer (11-bit) | ✗ | Stores role id | Foreign key reference to related record |
| `programme_id` | Integer (11-bit) | ✓ | Stores programme id | Foreign key reference to related record |
| `is_active` | Integer (1-bit) | ✓ | Stores is active | Status flag for filtering and workflow control |
| `must_change_password` | Integer (1-bit) | ✓ | Stores must change password | Reference value |
| `reset_token_hash` | String (max 64 characters) | ✓ | SHA-256 hash of reset token | Reference value |
| `reset_token_expires_at` | DateTime | ✓ | Token expiry (15 minutes) | Temporal tracking for audit and analysis |
| `last_login` | DateTime | ✓ | Stores last login | Reference value |
| `failed_login_attempts` | Integer (11-bit) | ✓ | Stores failed login attempts | Reference value |
| `account_locked_until` | DateTime | ✓ | Stores account locked until | Reference value |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |
| `updated_at` | DateTime | ✗ | Stores updated at | Temporal tracking for audit and analysis |
| `created_by` | Integer (11-bit) | ✓ | Stores created by | Reference value |

## Column Descriptions and Usage

### user_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores user id. Use this to establish relationships with other tables. 

### email

- **Type:** String (max 100 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores email. 

### alternate_email

- **Type:** String (max 255 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores alternate email. 

### password

- **Type:** String (max 255 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores password. 

### first_name

- **Type:** String (max 50 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores first name. 

### last_name

- **Type:** String (max 50 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores last name. 

### phone

- **Type:** String (max 20 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores phone. 

### role_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores role id. Use this to establish relationships with other tables. 

### programme_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores programme id. Use this to establish relationships with other tables. 

### is_active

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is active. Use boolean logic to include/exclude records in queries and business logic. 

### must_change_password

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores must change password. 

### reset_token_hash

- **Type:** String (max 64 characters)
- **Nullability:** Nullable
- **Description:** SHA-256 hash of reset token

**Usage Notes:**
This column stores reset token hash. 

### reset_token_expires_at

- **Type:** DateTime
- **Nullability:** Nullable
- **Description:** Token expiry (15 minutes)

**Usage Notes:**
This column stores reset token expires at. Use this column for temporal queries, sorting, and audit trails. 

### last_login

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores last login. 

### failed_login_attempts

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores failed login attempts. 

### account_locked_until

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores account locked until. 

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

### created_by

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores created by. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

