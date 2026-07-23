# indicator_capture_history

## Table Purpose

Audit trail documenting all changes to indicator captures, including who made changes and when.

**Common Use Cases:** Change tracking, audit compliance, version control, activity investigation

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `history_id` | Integer (11-bit) | ✗ | Stores history id | Foreign key reference to related record |
| `capture_id` | Integer (11-bit) | ✗ | Stores capture id | Foreign key reference to related record |
| `version_number` | Integer (11-bit) | ✗ | Stores version number | Reference value |
| `field_changed` | String (max 100 characters) | ✗ | Stores field changed | Reference value |
| `old_value` | Long Text | ✓ | Stores old value | Reference value |
| `new_value` | Long Text | ✓ | Stores new value | Reference value |
| `changed_by` | Integer (11-bit) | ✗ | Stores changed by | Reference value |
| `changed_at` | DateTime | ✗ | Stores changed at | Temporal tracking for audit and analysis |
| `change_reason` | String (max 255 characters) | ✓ | Stores change reason | Reference value |

## Column Descriptions and Usage

### history_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores history id. Use this to establish relationships with other tables. 

### capture_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores capture id. Use this to establish relationships with other tables. 

### version_number

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores version number. 

### field_changed

- **Type:** String (max 100 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores field changed. 

### old_value

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores old value. 

### new_value

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores new value. 

### changed_by

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores changed by. 

### changed_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores changed at. Use this column for temporal queries, sorting, and audit trails. 

### change_reason

- **Type:** String (max 255 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores change reason. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

