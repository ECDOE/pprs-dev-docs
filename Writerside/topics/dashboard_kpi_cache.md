# dashboard_kpi_cache

## Table Purpose

Caches calculated KPI metrics for dashboard display to optimize rendering performance.

**Common Use Cases:** Dashboard performance optimization, metric caching, variance calculation storage

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `cache_id` | Integer (11-bit) | ✗ | Stores cache id | Foreign key reference to related record |
| `programme_id` | Integer (11-bit) | ✓ | Stores programme id | Foreign key reference to related record |
| `indicator_id` | Integer (11-bit) | ✓ | Stores indicator id | Foreign key reference to related record |
| `quarter_id` | Integer (11-bit) | ✗ | Stores quarter id | Foreign key reference to related record |
| `year_id` | Integer (11-bit) | ✗ | Stores year id | Foreign key reference to related record |
| `metric_name` | String (max 100 characters) | ✗ | Stores metric name | Reference value |
| `metric_value` | Decimal Number | ✓ | Stores metric value | Reference value |
| `metric_target` | Decimal Number | ✓ | Stores metric target | Reference value |
| `variance_percentage` | Decimal Number | ✓ | Stores variance percentage | Reference value |
| `status` | String (max 50 characters) | ✓ | Stores status | Workflow or state tracking |
| `last_updated` | DateTime | ✗ | Stores last updated | Reference value |

## Column Descriptions and Usage

### cache_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores cache id. Use this to establish relationships with other tables. 

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
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores quarter id. Use this to establish relationships with other tables. 

### year_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores year id. Use this to establish relationships with other tables. 

### metric_name

- **Type:** String (max 100 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores metric name. 

### metric_value

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores metric value. 

### metric_target

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores metric target. 

### variance_percentage

- **Type:** Decimal Number
- **Nullability:** Nullable

**Usage Notes:**
This column stores variance percentage. 

### status

- **Type:** String (max 50 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores status. Filter records by status to identify items at specific workflow stages. 

### last_updated

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores last updated. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

