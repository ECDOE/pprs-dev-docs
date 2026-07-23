# strategic_review_drafts

## Table Purpose

Captures preliminary review notes on indicator captures during the strategic review process.

**Common Use Cases:** Strategic review workflow, proof of evidence verification, decision documentation

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `draft_id` | Integer (11-bit) | ✗ | Stores draft id | Foreign key reference to related record |
| `capture_id` | Integer (11-bit) | ✗ | Stores capture id | Foreign key reference to related record |
| `reviewed_by` | Integer (11-bit) | ✗ | Stores reviewed by | Reference value |
| `decision` | String (max 20 characters) | ✓ | Stores decision | Reference value |
| `poe_verified` | Integer (1-bit) | ✓ | Stores poe verified | Reference value |
| `rejection_reason` | Long Text | ✓ | Stores rejection reason | Reference value |
| `comments` | Long Text | ✓ | Stores comments | Reference value |
| `created_at` | DateTime | ✓ | Stores created at | Temporal tracking for audit and analysis |
| `updated_at` | DateTime | ✓ | Stores updated at | Temporal tracking for audit and analysis |

## Column Descriptions and Usage

### draft_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores draft id. Use this to establish relationships with other tables. 

### capture_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores capture id. Use this to establish relationships with other tables. 

### reviewed_by

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores reviewed by. 

### decision

- **Type:** String (max 20 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores decision. 

### poe_verified

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores poe verified. 

### rejection_reason

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores rejection reason. 

### comments

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores comments. 

### created_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores created at. Use this column for temporal queries, sorting, and audit trails. 

### updated_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores updated at. Use this column for temporal queries, sorting, and audit trails. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

