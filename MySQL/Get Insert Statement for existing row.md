## Get Insert Statement for existing row
```sql
SELECT 
  CONCAT(
    'INSERT INTO `company` (`id`, `code`, `short_name`, `name_en`, `name_kh`, `created_by`, `updated_by`, `flag`, `created_at`, `updated_at`, `deleted_at`) VALUES ',
      GROUP_CONCAT(
        CONCAT('\n ("',`id`,'","',`code`,'", "',`short_name`,'", "',`name_en`,'", "',`name_kh`,'","',`created_by`,'","',`updated_by`,'","',`flag`,'","',`created_at`,'","',`updated_at`,'","',`deleted_at`,'")')
      ), ';'
  ) AS query
FROM `company`
```
