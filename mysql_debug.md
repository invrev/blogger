SHOW VARIABLES LIKE '%heap%' 
SHOW VARIABLES LIKE '%tmp_table_size%'; 
SHOW VARIABLES LIKE '%max%'; 
SHOW FULL PROCESSLIST;
SELECT table_schema "Data Base Name", sum( data_length + index_length ) / 1024 / 1024/1024
"Data Base Size in GB", sum( data_free )/ 1024 / 1024 "Free Space in MB"
FROM information_schema.TABLES GROUP BY table_schema;
SHOW ENGINE INNODB STATUS;

