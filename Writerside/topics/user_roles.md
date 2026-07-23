# user_roles

## Table Purpose

Defines organizational roles and their associated permissions within the indicator management system.

**Common Use Cases:** Access control, permission assignment, role-based UI rendering

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `role_id` | Integer (11-bit) | ✗ | Stores role id | Foreign key reference to related record |
| `role_name` | String (max 50 characters) | ✗ | Stores role name | Reference value |
| `role_description` | Long Text | ✓ | Stores role description | Reference value |
| `can_capture_data` | Integer (1-bit) | ✓ | Stores can capture data | Reference value |
| `can_approve_data` | Integer (1-bit) | ✓ | Stores can approve data | Reference value |
| `can_view_dashboard` | Integer (1-bit) | ✓ | Stores can view dashboard | Reference value |
| `can_export_reports` | Integer (1-bit) | ✓ | Stores can export reports | Reference value |
| `can_manage_users` | Integer (1-bit) | ✓ | Stores can manage users | Reference value |
| `can_manage_programmes` | Integer (1-bit) | ✓ | Stores can manage programmes | Reference value |
| `is_read_only` | Integer (1-bit) | ✓ | Stores is read only | Reference value |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### role_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores role id. Use this to establish relationships with other tables. 

### role_name

- **Type:** String (max 50 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores role name. 

### role_description

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores role description. 

### can_capture_data

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores can capture data. 

### can_approve_data

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores can approve data. 

### can_view_dashboard

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores can view dashboard. 

### can_export_reports

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores can export reports. 

### can_manage_users

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores can manage users. 

### can_manage_programmes

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores can manage programmes. 

### is_read_only

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is read only. Use boolean logic to include/exclude records in queries and business logic. 

### created_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores created at. Use this column for temporal queries, sorting, and audit trails. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

