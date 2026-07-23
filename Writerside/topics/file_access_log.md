# file_access_log

## Table Purpose

Tracks file download and access activities for audit and compliance purposes.

**Common Use Cases:** File access audit, compliance reporting, security monitoring

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `access_log_id` | Integer (20-bit) | ✗ | Stores access log id | Foreign key reference to related record |
| `file_id` | Integer (11-bit) | ✗ | Stores file id | Foreign key reference to related record |
| `user_id` | Integer (11-bit) | ✗ | Stores user id | Foreign key reference to related record |
| `access_type` | Enumeration: view, download, preview, delete, modify | ✗ | Stores access type | Reference value |
| `access_timestamp` | DateTime | ✗ | Stores access timestamp | Reference value |
| `ip_address` | String (max 45 characters) | ✓ | Stores ip address | Reference value |
| `user_agent` | Long Text | ✓ | Browser/device info | Reference value |
| `download_size_bytes` | Integer (20-bit) | ✓ | How much was downloaded | Reference value |
| `success` | Integer (1-bit) | ✓ | Stores success | Reference value |
| `error_message` | Long Text | ✓ | Stores error message | Reference value |

## Column Descriptions and Usage

### access_log_id

- **Type:** Integer (20-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores access log id. Use this to establish relationships with other tables. 

### file_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores file id. Use this to establish relationships with other tables. 

### user_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores user id. Use this to establish relationships with other tables. 

### access_type

- **Type:** Enumeration: view, download, preview, delete, modify
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores access type. 

### access_timestamp

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores access timestamp. 

### ip_address

- **Type:** String (max 45 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores ip address. 

### user_agent

- **Type:** Long Text
- **Nullability:** Nullable
- **Description:** Browser/device info

**Usage Notes:**
This column stores user agent. 

### download_size_bytes

- **Type:** Integer (20-bit)
- **Nullability:** Nullable
- **Description:** How much was downloaded

**Usage Notes:**
This column stores download size bytes. 

### success

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores success. 

### error_message

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores error message. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

