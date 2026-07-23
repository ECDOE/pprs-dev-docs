# notifications

## Table Purpose

Stores system-generated notifications for users regarding approvals, rejections, and deadline reminders.

**Common Use Cases:** User communication, workflow alerts, deadline warnings

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `notification_id` | Integer (11-bit) | ✗ | Stores notification id | Foreign key reference to related record |
| `user_id` | Integer (11-bit) | ✗ | Stores user id | Foreign key reference to related record |
| `notification_type` | Enumeration: rejection, approval_required, approved, reminder, system, cp_review_required, cp_approved, cp_rejected, deadline_warning | ✗ | Stores notification type | Reference value |
| `title` | String (max 200 characters) | ✗ | Stores title | Reference value |
| `message` | Long Text | ✗ | Stores message | Reference value |
| `related_capture_id` | Integer (11-bit) | ✓ | Stores related capture id | Foreign key reference to related record |
| `related_programme_id` | Integer (11-bit) | ✓ | Stores related programme id | Foreign key reference to related record |
| `is_read` | Integer (1-bit) | ✓ | Stores is read | Reference value |
| `read_at` | DateTime | ✓ | Stores read at | Temporal tracking for audit and analysis |
| `priority` | Enumeration: low, medium, high | ✓ | Stores priority | Reference value |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### notification_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores notification id. Use this to establish relationships with other tables. 

### user_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores user id. Use this to establish relationships with other tables. 

### notification_type

- **Type:** Enumeration: rejection, approval_required, approved, reminder, system, cp_review_required, cp_approved, cp_rejected, deadline_warning
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores notification type. 

### title

- **Type:** String (max 200 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores title. 

### message

- **Type:** Long Text
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores message. 

### related_capture_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores related capture id. Use this to establish relationships with other tables. 

### related_programme_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores related programme id. Use this to establish relationships with other tables. 

### is_read

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is read. Use boolean logic to include/exclude records in queries and business logic. 

### read_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores read at. Use this column for temporal queries, sorting, and audit trails. 

### priority

- **Type:** Enumeration: low, medium, high
- **Nullability:** Nullable

**Usage Notes:**
This column stores priority. 

### created_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores created at. Use this column for temporal queries, sorting, and audit trails. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

