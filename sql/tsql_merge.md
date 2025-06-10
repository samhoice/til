# Merge - the way to do insert or update in TSQL

Today I was looking for a way to do an atomic update in TSQL and came across `MERGE`, which is exactly that. The basic idea is:

```sql
MERGE target_table AS target
USING (VALUES (@param1, @param2, @param3)) AS source (col1, col2, col3)
ON target.id = source.col1
WHEN MATCHED THEN
    UPDATE SET col2 = source.col2, col3 = source.col3
WHEN NOT MATCHED THEN
    INSERT (col1, col2, col3) VALUES (source.col1, source.col2, source.col3);
```

And claude's example was:

```sql
MERGE Users AS target
USING (VALUES (@UserId, @Name, @Email)) AS source (UserId, Name, Email)
ON target.UserId = source.UserId
WHEN MATCHED THEN
    UPDATE SET Name = source.Name, Email = source.Email
WHEN NOT MATCHED THEN
    INSERT (UserId, Name, Email) VALUES (source.UserId, source.Name, source.Email);
```

Because claude is always about User tables.
