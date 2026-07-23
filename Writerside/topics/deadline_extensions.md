# deadline_extensions

## Table Purpose

Tracks deadline extension requests granted to users or programmes for indicator capture submissions.

**Common Use Cases:** Exceptional deadline management, audit trail for extensions, justification documentation

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `extension_id` | Integer (11-bit) | ✗ | Stores extension id | Foreign key reference to related record |
| `user_id` | Integer (11-bit) | ✗ | User granted extension | Foreign key reference to related record |
| `capture_id` | Integer (11-bit) | ✓ | Specific capture (if applicable) | Foreign key reference to related record |
| `programme_id` | Integer (11-bit) | ✓ | Or entire programme | Foreign key reference to related record |
| `deadline_type` | Enumeration: capturer, pm, cp | ✗ | Stores deadline type | Reference value |
| `original_deadline` | DateTime | ✗ | Stores original deadline | Reference value |
| `extended_deadline` | DateTime | ✗ | Stores extended deadline | Reference value |
| `extension_reason` | Long Text | ✗ | Stores extension reason | Reference value |
| `granted_by` | Integer (11-bit) | ✗ | Stores granted by | Reference value |
| `granted_at` | DateTime | ✗ | Stores granted at | Temporal tracking for audit and analysis |
| `is_active` | Integer (1-bit) | ✓ | Stores is active | Status flag for filtering and workflow control |

## Column Descriptions and Usage

### extension_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores extension id. Use this to establish relationships with other tables. 

### user_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)
- **Description:** User granted extension

**Usage Notes:**
This column stores user id. Use this to establish relationships with other tables. 

### capture_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable
- **Description:** Specific capture (if applicable)

**Usage Notes:**
This column stores capture id. Use this to establish relationships with other tables. 

### programme_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable
- **Description:** Or entire programme

**Usage Notes:**
This column stores programme id. Use this to establish relationships with other tables. 

### deadline_type

- **Type:** Enumeration: capturer, pm, cp
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores deadline type. 

### original_deadline

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores original deadline. 

### extended_deadline

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores extended deadline. 

### extension_reason

- **Type:** Long Text
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores extension reason. 

### granted_by

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores granted by. 

### granted_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores granted at. Use this column for temporal queries, sorting, and audit trails. 

### is_active

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is active. Use boolean logic to include/exclude records in queries and business logic. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

