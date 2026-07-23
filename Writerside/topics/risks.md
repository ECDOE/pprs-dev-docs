# risks

## Table Purpose

Captures programme-level risks, their mitigation strategies, and tracking of mitigation progress.

**Common Use Cases:** Risk management, mitigation tracking, programme health assessment

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `risk_id` | Integer (11-bit) | ✗ | Stores risk id | Foreign key reference to related record |
| `programme_id` | Integer (11-bit) | ✗ | Stores programme id | Foreign key reference to related record |
| `risk_title` | String (max 200 characters) | ✗ | Stores risk title | Reference value |
| `risk_description` | Long Text | ✗ | Stores risk description | Reference value |
| `risk_category` | String (max 100 characters) | ✓ | Stores risk category | Reference value |
| `severity` | Enumeration: low, medium, high | ✓ | Stores severity | Reference value |
| `likelihood` | Enumeration: low, medium, high | ✓ | Stores likelihood | Reference value |
| `impact` | Enumeration: low, medium, high | ✓ | Stores impact | Reference value |
| `mitigation_strategy` | Long Text | ✓ | Stores mitigation strategy | Reference value |
| `mitigation_status` | Enumeration: not_started, in_progress, completed | ✓ | Stores mitigation status | Workflow or state tracking |
| `owner_id` | Integer (11-bit) | ✓ | Stores owner id | Foreign key reference to related record |
| `identified_date` | Date | ✗ | Stores identified date | Temporal tracking for audit and analysis |
| `review_date` | Date | ✓ | Stores review date | Temporal tracking for audit and analysis |
| `is_active` | Integer (1-bit) | ✓ | Stores is active | Status flag for filtering and workflow control |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |
| `updated_at` | DateTime | ✗ | Stores updated at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### risk_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores risk id. Use this to establish relationships with other tables. 

### programme_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores programme id. Use this to establish relationships with other tables. 

### risk_title

- **Type:** String (max 200 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores risk title. 

### risk_description

- **Type:** Long Text
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores risk description. 

### risk_category

- **Type:** String (max 100 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores risk category. 

### severity

- **Type:** Enumeration: low, medium, high
- **Nullability:** Nullable

**Usage Notes:**
This column stores severity. 

### likelihood

- **Type:** Enumeration: low, medium, high
- **Nullability:** Nullable

**Usage Notes:**
This column stores likelihood. 

### impact

- **Type:** Enumeration: low, medium, high
- **Nullability:** Nullable

**Usage Notes:**
This column stores impact. 

### mitigation_strategy

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores mitigation strategy. 

### mitigation_status

- **Type:** Enumeration: not_started, in_progress, completed
- **Nullability:** Nullable

**Usage Notes:**
This column stores mitigation status. Filter records by status to identify items at specific workflow stages. 

### owner_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores owner id. Use this to establish relationships with other tables. 

### identified_date

- **Type:** Date
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores identified date. Use this column for temporal queries, sorting, and audit trails. 

### review_date

- **Type:** Date
- **Nullability:** Nullable

**Usage Notes:**
This column stores review date. Use this column for temporal queries, sorting, and audit trails. 

### is_active

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is active. Use boolean logic to include/exclude records in queries and business logic. 

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

