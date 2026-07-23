# data_access_log

## Table Purpose

Records access to sensitive programme and indicator data for audit and compliance requirements.

**Common Use Cases:** Data access auditing, compliance investigation, security monitoring

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `access_id` | Integer (20-bit) | ✗ | Stores access id | Foreign key reference to related record |
| `user_id` | Integer (11-bit) | ✗ | Stores user id | Foreign key reference to related record |
| `access_type` | String (max 50 characters) | ✗ | Stores access type | Reference value |
| `data_type` | String (max 100 characters) | ✗ | Stores data type | Reference value |
| `programme_id` | Integer (11-bit) | ✓ | Stores programme id | Foreign key reference to related record |
| `indicator_id` | Integer (11-bit) | ✓ | Stores indicator id | Foreign key reference to related record |
| `quarter_id` | Integer (11-bit) | ✓ | Stores quarter id | Foreign key reference to related record |
| `year_id` | Integer (11-bit) | ✓ | Stores year id | Foreign key reference to related record |
| `access_timestamp` | DateTime | ✗ | Stores access timestamp | Reference value |
| `ip_address` | String (max 45 characters) | ✓ | Stores ip address | Reference value |
| `export_format` | String (max 20 characters) | ✓ | Stores export format | Reference value |

## Column Descriptions and Usage

### access_id

- **Type:** Integer (20-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores access id. Use this to establish relationships with other tables. 

### user_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores user id. Use this to establish relationships with other tables. 

### access_type

- **Type:** String (max 50 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores access type. 

### data_type

- **Type:** String (max 100 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores data type. 

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

### quarter_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores quarter id. Use this to establish relationships with other tables. 

### year_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores year id. Use this to establish relationships with other tables. 

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

### export_format

- **Type:** String (max 20 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores export format. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

