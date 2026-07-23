# indicator_technical_details

## Table Purpose

Provides detailed technical specifications, definitions, and calculation methodology for each outcome indicator.

**Common Use Cases:** Indicator documentation, data validation, means of verification, calculation guidance

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `technical_detail_id` | Integer (11-bit) | ✗ | Stores technical detail id | Foreign key reference to related record |
| `indicator_id` | Integer (11-bit) | ✗ | FK to outcome_indicators.indicator_id, one row per indicator | Foreign key reference to related record |
| `definition` | Long Text | ✓ | Full definition of the indicator | Reference value |
| `source_of_data` | Long Text | ✓ | Stores source of data | Reference value |
| `method_of_calculation` | Long Text | ✓ | Method of Calculation / Assessment | Reference value |
| `means_of_verification` | Long Text | ✓ | Stores means of verification | Reference value |
| `assumptions` | Long Text | ✓ | Stores assumptions | Reference value |
| `target_women` | String (max 255 characters) | ✓ | Disaggregation of Beneficiaries: Women | Reference value |
| `target_youth` | String (max 255 characters) | ✓ | Disaggregation of Beneficiaries: Youth | Reference value |
| `target_disabilities` | String (max 255 characters) | ✓ | Disaggregation of Beneficiaries: Persons with Disabilities | Reference value |
| `spatial_transformation` | Long Text | ✓ | Stores spatial transformation | Reference value |
| `calculation_type` | String (max 50 characters) | ✓ | e.g. Non-cumulative, Cumulative Year-End | Reference value |
| `reporting_cycle` | String (max 50 characters) | ✓ | e.g. Quarterly, Annually | Reference value |
| `desired_performance` | Long Text | ✓ | Stores desired performance | Reference value |
| `indicator_responsibility` | String (max 255 characters) | ✓ | Director/unit accountable for the indicator | Reference value |
| `created_at` | DateTime | ✗ | Stores created at | Temporal tracking for audit and analysis |
| `updated_at` | DateTime | ✗ | Stores updated at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### technical_detail_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores technical detail id. Use this to establish relationships with other tables. 

### indicator_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)
- **Description:** FK to outcome_indicators.indicator_id, one row per indicator

**Usage Notes:**
This column stores indicator id. Use this to establish relationships with other tables. 

### definition

- **Type:** Long Text
- **Nullability:** Nullable
- **Description:** Full definition of the indicator

**Usage Notes:**
This column stores definition. 

### source_of_data

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores source of data. 

### method_of_calculation

- **Type:** Long Text
- **Nullability:** Nullable
- **Description:** Method of Calculation / Assessment

**Usage Notes:**
This column stores method of calculation. 

### means_of_verification

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores means of verification. 

### assumptions

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores assumptions. 

### target_women

- **Type:** String (max 255 characters)
- **Nullability:** Nullable
- **Description:** Disaggregation of Beneficiaries: Women

**Usage Notes:**
This column stores target women. 

### target_youth

- **Type:** String (max 255 characters)
- **Nullability:** Nullable
- **Description:** Disaggregation of Beneficiaries: Youth

**Usage Notes:**
This column stores target youth. 

### target_disabilities

- **Type:** String (max 255 characters)
- **Nullability:** Nullable
- **Description:** Disaggregation of Beneficiaries: Persons with Disabilities

**Usage Notes:**
This column stores target disabilities. 

### spatial_transformation

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores spatial transformation. 

### calculation_type

- **Type:** String (max 50 characters)
- **Nullability:** Nullable
- **Description:** e.g. Non-cumulative, Cumulative Year-End

**Usage Notes:**
This column stores calculation type. 

### reporting_cycle

- **Type:** String (max 50 characters)
- **Nullability:** Nullable
- **Description:** e.g. Quarterly, Annually

**Usage Notes:**
This column stores reporting cycle. 

### desired_performance

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores desired performance. 

### indicator_responsibility

- **Type:** String (max 255 characters)
- **Nullability:** Nullable
- **Description:** Director/unit accountable for the indicator

**Usage Notes:**
This column stores indicator responsibility. 

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

