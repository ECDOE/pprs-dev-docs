# user_activity_log

## Table Purpose

Records all system activities for audit, compliance, and security monitoring purposes.

**Common Use Cases:** Activity auditing, security investigation, compliance reporting, performance analysis

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `activity_id` | Integer (20-bit) | ✗ | Stores activity id | Foreign key reference to related record |
| `session_id` | Integer (11-bit) | ✓ | Stores session id | Foreign key reference to related record |
| `user_id` | Integer (11-bit) | ✗ | Stores user id | Foreign key reference to related record |
| `activity_type` | String (max 100 characters) | ✗ | Stores activity type | Reference value |
| `activity_category` | String (max 50 characters) | ✓ | Stores activity category | Reference value |
| `activity_description` | Long Text | ✗ | Stores activity description | Reference value |
| `login_method` | String (max 50 characters) | ✓ | Stores login method | Reference value |
| `affected_table` | String (max 100 characters) | ✓ | Stores affected table | Reference value |
| `affected_record_id` | Integer (11-bit) | ✓ | Stores affected record id | Foreign key reference to related record |
| `programme_id` | Integer (11-bit) | ✓ | Stores programme id | Foreign key reference to related record |
| `indicator_id` | Integer (11-bit) | ✓ | Stores indicator id | Foreign key reference to related record |
| `ip_address` | String (max 45 characters) | ✗ | Stores ip address | Reference value |
| `user_agent` | Long Text | ✓ | Stores user agent | Reference value |
| `request_method` | String (max 10 characters) | ✓ | Stores request method | Reference value |
| `request_url` | String (max 500 characters) | ✓ | Stores request url | Reference value |
| `old_values` | Long Text | ✓ | Stores old values | Reference value |
| `new_values` | Long Text | ✓ | Stores new values | Reference value |
| `activity_status` | Enumeration: success, failed, partial | ✓ | Stores activity status | Workflow or state tracking |
| `error_message` | Long Text | ✓ | Stores error message | Reference value |
| `activity_timestamp` | DateTime | ✗ | Stores activity timestamp | Reference value |
| `response_time_ms` | Integer (11-bit) | ✓ | Stores response time ms | Reference value |

## Column Descriptions and Usage

### activity_id

- **Type:** Integer (20-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores activity id. Use this to establish relationships with other tables. 

### session_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores session id. Use this to establish relationships with other tables. 

### user_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores user id. Use this to establish relationships with other tables. 

### activity_type

- **Type:** String (max 100 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores activity type. 

### activity_category

- **Type:** String (max 50 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores activity category. 

### activity_description

- **Type:** Long Text
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores activity description. 

### login_method

- **Type:** String (max 50 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores login method. 

### affected_table

- **Type:** String (max 100 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores affected table. 

### affected_record_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores affected record id. Use this to establish relationships with other tables. 

### programme_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores programme id. Use this to establish relationships with other tables. 

### indicator_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores indicator id. Use this to establish relationships with other tables. 

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

### request_method

- **Type:** String (max 10 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores request method. 

### request_url

- **Type:** String (max 500 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores request url. 

### old_values

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores old values. 

### new_values

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores new values. 

### activity_status

- **Type:** Enumeration: success, failed, partial
- **Nullability:** Nullable

**Usage Notes:**
This column stores activity status. Filter records by status to identify items at specific workflow stages. 

### error_message

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores error message. 

### activity_timestamp

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores activity timestamp. 

### response_time_ms

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores response time ms. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

