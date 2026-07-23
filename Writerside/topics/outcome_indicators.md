# outcome_indicators

## Table Purpose

Defines measurable key result areas that indicate performance against strategic objectives.

**Common Use Cases:** Performance tracking, annual target setting, quarterly data capture, reporting and analysis

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `indicator_id` | Integer (11-bit) | ✗ | Stores indicator id | Foreign key reference to related record |
| `indicator_code` | String (max 20 characters) | ✗ | Stores indicator code | Reference value |
| `indicator_description` | Long Text | ✓ | Stores indicator description | Reference value |
| `outcomes` | Long Text | ✓ | Stores outcomes | Reference value |
| `programme_id` | Integer (11-bit) | ✗ | Stores programme id | Foreign key reference to related record |
| `measurement_unit` | String (max 50 characters) | ✓ | Stores measurement unit | Reference value |
| `annual_target_type` | String (max 20 characters) | ✓ | Stores annual target type | Reference value |
| `is_active` | Integer (1-bit) | ✓ | Stores is active | Status flag for filtering and workflow control |
| `responsibility_manager` | String (max 100 characters) | ✓ | Stores responsibility manager | Reference value |
| `display_order` | Integer (11-bit) | ✓ | Stores display order | Reference value |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |
| `updated_at` | DateTime | ✗ | Stores updated at | Temporal tracking for audit and analysis |
| `is_cumulative` | Integer (1-bit) | ✓ | FALSE for indicators like "number of schools" that dont accumulate quarterly | Reference value |
| `calculation_method` | Enumeration: sum, average, latest, percentage | ✓ | How to calculate annual from quarterly | Reference value |

## Column Descriptions and Usage

### indicator_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores indicator id. Use this to establish relationships with other tables. 

### indicator_code

- **Type:** String (max 20 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores indicator code. 

### indicator_description

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores indicator description. 

### outcomes

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores outcomes. 

### programme_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores programme id. Use this to establish relationships with other tables. 

### measurement_unit

- **Type:** String (max 50 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores measurement unit. 

### annual_target_type

- **Type:** String (max 20 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores annual target type. 

### is_active

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is active. Use boolean logic to include/exclude records in queries and business logic. 

### responsibility_manager

- **Type:** String (max 100 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores responsibility manager. 

### display_order

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores display order. 

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

### is_cumulative

- **Type:** Integer (1-bit)
- **Nullability:** Nullable
- **Description:** FALSE for indicators like "number of schools" that dont accumulate quarterly

**Usage Notes:**
This column stores is cumulative. Use boolean logic to include/exclude records in queries and business logic. 

### calculation_method

- **Type:** Enumeration: sum, average, latest, percentage
- **Nullability:** Nullable
- **Description:** How to calculate annual from quarterly

**Usage Notes:**
This column stores calculation method. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

