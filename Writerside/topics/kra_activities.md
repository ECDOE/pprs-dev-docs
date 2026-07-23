# kra_activities

## Table Purpose

Represents specific activities and deliverables within key result areas, supporting performance measurement.

**Common Use Cases:** Activity tracking, workplan management, resource allocation

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `activity_id` | Integer (11-bit) | ✗ | Stores activity id | Foreign key reference to related record |
| `kra_id` | Integer (11-bit) | ✗ | Stores kra id | Foreign key reference to related record |
| `activity_name` | String (max 255 characters) | ✗ | Stores activity name | Reference value |
| `activity_description` | Long Text | ✓ | Stores activity description | Reference value |
| `target_date` | Date | ✓ | Stores target date | Temporal tracking for audit and analysis |
| `progress_percentage` | Integer (11-bit) | ✓ | Stores progress percentage | Reference value |
| `status` | Enumeration: not_started, in_progress, completed, delayed | ✓ | Stores status | Workflow or state tracking |
| `responsible_person` | String (max 100 characters) | ✓ | Stores responsible person | Reference value |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |
| `updated_at` | DateTime | ✗ | Stores updated at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### activity_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores activity id. Use this to establish relationships with other tables. 

### kra_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores kra id. Use this to establish relationships with other tables. 

### activity_name

- **Type:** String (max 255 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores activity name. 

### activity_description

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores activity description. 

### target_date

- **Type:** Date
- **Nullability:** Nullable

**Usage Notes:**
This column stores target date. Use this column for temporal queries, sorting, and audit trails. 

### progress_percentage

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores progress percentage. 

### status

- **Type:** Enumeration: not_started, in_progress, completed, delayed
- **Nullability:** Nullable

**Usage Notes:**
This column stores status. Filter records by status to identify items at specific workflow stages. 

### responsible_person

- **Type:** String (max 100 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores responsible person. 

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

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

