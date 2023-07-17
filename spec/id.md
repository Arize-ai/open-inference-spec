# ID

ID is a reserved singleton category for the row. It is used to uniquely identify the inference record. It is typically a UUID. ID columns are prefixed with the category `:id:` in the column name. ID columns are strings and SHOULD be unique. There is no reserved **specifier** or **name** for IDs. For this reason, `:id:` and `:id.str:` are all the valid ID columns.
