# uploaded_files

## Table Purpose

Manages file attachments related to indicator captures and programmes, including storage location and access controls.

**Common Use Cases:** Evidence documentation, proof of data, file versioning, access control

## Column Reference

| Column | Type | Nullable | Meaning | Usage |
|--------|------|----------|---------|-------|
| `file_id` | Integer (11-bit) | ✗ | Stores file id | Foreign key reference to related record |
| `file_name` | String (max 255 characters) | ✗ | Stores file name | Reference value |
| `file_original_name` | String (max 255 characters) | ✗ | Stores file original name | Reference value |
| `file_path` | String (max 500 characters) | ✗ | Stores file path | Reference value |
| `file_size_bytes` | Integer (20-bit) | ✗ | Stores file size bytes | Reference value |
| `file_extension` | String (max 10 characters) | ✗ | Stores file extension | Reference value |
| `file_category` | String (max 50 characters) | ✓ | Stores file category | Reference value |
| `storage_type` | Enumeration: local, google_drive, onedrive, dropbox | ✓ | Where file is stored | Reference value |
| `cloud_link` | Long Text | ✓ | Full URL to Google Drive/OneDrive file | Reference value |
| `cloud_shared_link` | Long Text | ✓ | Public sharing link | Reference value |
| `is_zip_container` | Integer (1-bit) | ✓ | TRUE if this is a ZIP with multiple files | Reference value |
| `zip_contents_count` | Integer (11-bit) | ✓ | Number of files in ZIP | Reference value |
| `zip_contents_list` | Long Text | ✓ | JSON array of files inside ZIP | Reference value |
| `mime_type` | String (max 100 characters) | ✓ | Detailed MIME type | Reference value |
| `file_hash` | String (max 64 characters) | ✓ | SHA-256 hash for integrity check | Reference value |
| `virus_scanned` | Integer (1-bit) | ✓ | Has antivirus check been done | Reference value |
| `virus_scan_result` | String (max 20 characters) | ✓ | clean, infected, pending, error | Reference value |
| `virus_scan_date` | DateTime | ✓ | Stores virus scan date | Temporal tracking for audit and analysis |
| `is_public` | Integer (1-bit) | ✓ | Can anyone with link access | Reference value |
| `access_level` | Enumeration: private, programme, department, public | ✓ | Who can access | Reference value |
| `download_count` | Integer (11-bit) | ✓ | Track downloads | Reference value |
| `last_accessed_at` | DateTime | ✓ | Stores last accessed at | Temporal tracking for audit and analysis |
| `last_accessed_by` | Integer (11-bit) | ✓ | Stores last accessed by | Reference value |
| `version_number` | Integer (11-bit) | ✓ | Stores version number | Reference value |
| `replaces_file_id` | Integer (11-bit) | ✓ | If this is new version, ID of old file | Foreign key reference to related record |
| `related_capture_id` | Integer (11-bit) | ✓ | Stores related capture id | Foreign key reference to related record |
| `related_programme_id` | Integer (11-bit) | ✓ | Stores related programme id | Foreign key reference to related record |
| `uploaded_by` | Integer (11-bit) | ✗ | Stores uploaded by | Reference value |
| `uploaded_at` | DateTime | ✗ | Stores uploaded at | Temporal tracking for audit and analysis |
| `description` | Long Text | ✓ | Stores description | Reference value |
| `is_deleted` | Integer (1-bit) | ✓ | Stores is deleted | Reference value |
| `deleted_at` | DateTime | ✓ | Stores deleted at | Temporal tracking for audit and analysis |
| `deleted_by` | Integer (11-bit) | ✓ | Stores deleted by | Reference value |
| `modified_at` | DateTime | ✓ | Stores modified at | Temporal tracking for audit and analysis |
| `modified_by` | Integer (11-bit) | ✓ | Stores modified by | Reference value |

## Column Descriptions and Usage

### file_id

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores file id. Use this to establish relationships with other tables. 

### file_name

- **Type:** String (max 255 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores file name. 

### file_original_name

- **Type:** String (max 255 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores file original name. 

### file_path

- **Type:** String (max 500 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores file path. 

### file_size_bytes

- **Type:** Integer (20-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores file size bytes. 

### file_extension

- **Type:** String (max 10 characters)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores file extension. 

### file_category

- **Type:** String (max 50 characters)
- **Nullability:** Nullable

**Usage Notes:**
This column stores file category. 

### storage_type

- **Type:** Enumeration: local, google_drive, onedrive, dropbox
- **Nullability:** Nullable
- **Description:** Where file is stored

**Usage Notes:**
This column stores storage type. 

### cloud_link

- **Type:** Long Text
- **Nullability:** Nullable
- **Description:** Full URL to Google Drive/OneDrive file

**Usage Notes:**
This column stores cloud link. 

### cloud_shared_link

- **Type:** Long Text
- **Nullability:** Nullable
- **Description:** Public sharing link

**Usage Notes:**
This column stores cloud shared link. 

### is_zip_container

- **Type:** Integer (1-bit)
- **Nullability:** Nullable
- **Description:** TRUE if this is a ZIP with multiple files

**Usage Notes:**
This column stores is zip container. Use boolean logic to include/exclude records in queries and business logic. 

### zip_contents_count

- **Type:** Integer (11-bit)
- **Nullability:** Nullable
- **Description:** Number of files in ZIP

**Usage Notes:**
This column stores zip contents count. 

### zip_contents_list

- **Type:** Long Text
- **Nullability:** Nullable
- **Description:** JSON array of files inside ZIP

**Usage Notes:**
This column stores zip contents list. 

### mime_type

- **Type:** String (max 100 characters)
- **Nullability:** Nullable
- **Description:** Detailed MIME type

**Usage Notes:**
This column stores mime type. 

### file_hash

- **Type:** String (max 64 characters)
- **Nullability:** Nullable
- **Description:** SHA-256 hash for integrity check

**Usage Notes:**
This column stores file hash. 

### virus_scanned

- **Type:** Integer (1-bit)
- **Nullability:** Nullable
- **Description:** Has antivirus check been done

**Usage Notes:**
This column stores virus scanned. 

### virus_scan_result

- **Type:** String (max 20 characters)
- **Nullability:** Nullable
- **Description:** clean, infected, pending, error

**Usage Notes:**
This column stores virus scan result. 

### virus_scan_date

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores virus scan date. Use this column for temporal queries, sorting, and audit trails. 

### is_public

- **Type:** Integer (1-bit)
- **Nullability:** Nullable
- **Description:** Can anyone with link access

**Usage Notes:**
This column stores is public. Use boolean logic to include/exclude records in queries and business logic. 

### access_level

- **Type:** Enumeration: private, programme, department, public
- **Nullability:** Nullable
- **Description:** Who can access

**Usage Notes:**
This column stores access level. 

### download_count

- **Type:** Integer (11-bit)
- **Nullability:** Nullable
- **Description:** Track downloads

**Usage Notes:**
This column stores download count. 

### last_accessed_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores last accessed at. Use this column for temporal queries, sorting, and audit trails. 

### last_accessed_by

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores last accessed by. 

### version_number

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores version number. 

### replaces_file_id

- **Type:** Integer (11-bit)
- **Nullability:** Nullable
- **Description:** If this is new version, ID of old file

**Usage Notes:**
This column stores replaces file id. Use this to establish relationships with other tables. 

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

### uploaded_by

- **Type:** Integer (11-bit)
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores uploaded by. 

### uploaded_at

- **Type:** DateTime
- **Nullability:** Required (NOT NULL)

**Usage Notes:**
This column stores uploaded at. Use this column for temporal queries, sorting, and audit trails. 

### description

- **Type:** Long Text
- **Nullability:** Nullable

**Usage Notes:**
This column stores description. 

### is_deleted

- **Type:** Integer (1-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores is deleted. Use boolean logic to include/exclude records in queries and business logic. 

### deleted_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores deleted at. Use this column for temporal queries, sorting, and audit trails. 

### deleted_by

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores deleted by. 

### modified_at

- **Type:** DateTime
- **Nullability:** Nullable

**Usage Notes:**
This column stores modified at. Use this column for temporal queries, sorting, and audit trails. 

### modified_by

- **Type:** Integer (11-bit)
- **Nullability:** Nullable

**Usage Notes:**
This column stores modified by. 

## Relationships and Cross-Table Usage

This table may be related to other tables through foreign keys. Refer to the indicated column names (those ending in `_id`) to understand join paths with other tables in the schema.

