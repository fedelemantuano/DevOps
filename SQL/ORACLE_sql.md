# Oracle SQL
Oracle SQL snippets

## Find Table/Object Owner
    #Table Owner
    SELECT owner, Table_name FROM all_tables WHERE Table_name='<table_name>';
    #Generic Object (es: a view is not a table)
    SELECT owner, object_name, object_type from ALL_OBJECTS where object_name = '<object_name>';

