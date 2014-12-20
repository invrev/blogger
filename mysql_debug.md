check mysql version
SELECT VERSION()

@ INNODB storage engine

SHOW VARIABLES LIKE '%heap%' 
SHOW VARIABLES LIKE '%tmp_table_size%'; 
SHOW VARIABLES LIKE '%max%'; 
SHOW FULL PROCESSLIST;
SELECT table_schema "Data Base Name", sum( data_length + index_length ) / 1024 / 1024/1024
"Data Base Size in GB", sum( data_free )/ 1024 / 1024 "Free Space in MB"
FROM information_schema.TABLES GROUP BY table_schema;
SHOW ENGINE INNODB STATUS;


use of clusered indexes
making choice of primary key
http://dev.mysql.com/doc/refman/5.0/en/innodb-index-types.html

Table space monitor
http://www.markleith.co.uk/2009/01/19/innodb-table-and-tablespace-monitors/
http://www.percona.com/blog/2006/07/17/show-innodb-status-walk-through/

INNODB monitor 

flush table
optimize table
analyze table


important variables

### #of connections

show variables like '%max_conn%'

show variables like '%innodb_max_purge_lag%'


current mysql page size = 16k
show variables like '%page_size%'



http://www.percona.com/blog/2006/06/04/innodb-page-size/

for datafiles and for buffer pool.
However this size can be changed if you need it for your workload.
go to file innobase/include/univ.i, lines:



UNIV_PAGE_SIZE is page size (as you see – default value 16Kb). Possible values for UNIV_PAGE_SIZE is 8K, 16K, 32K, 64K. You also have to change UNIV_PAGE_SIZE_SHIFT (according comment it must be 2-logarithm of UNIV_PAGE_SIZE).
For pagesize 8K – UNIV_PAGE_SIZE_SHIFT=13, for 32K – UNIV_PAGE_SIZE_SHIFT=15 and so on.


Yes. Playing with different page sizes is good thing to try if you’re trying to get maximum performance. Too bad Innodb currently does not allow to specify it for table or index but it has to be global and requires server rebuild. Generally for certain OLTP workloads you might like to have smaller pages as these allow more distinct peices of data to be in buffer pool. For DSS workloads which require large scans or deal with large rows on the contrary large pages could be good to avoid fragmentation.


#Load the data from the file
http://www.percona.com/blog/2008/07/03/how-to-load-large-files-safely-into-innodb-with-load-data-infile/


#Setting up or modifying the dirty pages

Dirty pages  :

These are pages that have been modified in memory, but not on disk.

#To update the values  use
SET GLOBAL innodb_old_blocks_time=250; // This is 0.25 seconds
SET GLOBAL innodb_old_blocks_pct=5;
SET GLOBAL innodb_max_dirty_pages_pct=0;


#Total buffer pool size
SELECT FORMAT(BufferPoolPages*PageSize/POWER(1024,3),2) TotalBufferPoolSizeGB FROM
(SELECT variable_value BufferPoolPages FROM information_schema.global_status
WHERE variable_name = 'Innodb_buffer_pool_pages_total') A,
(SELECT variable_value PageSize FROM information_schema.global_status
WHERE variable_name = 'Innodb_page_size') B;

#Used buffer pool size
SELECT FORMAT(BufferPoolPages*PageSize/POWER(1024,3),2) UsedBufferPoolSizeGB FROM
(SELECT variable_value BufferPoolPages FROM information_schema.global_status
WHERE variable_name = 'Innodb_buffer_pool_pages_data') A,
(SELECT variable_value PageSize FROM information_schema.global_status
WHERE variable_name = 'Innodb_page_size') B;

SELECT CONCAT(FORMAT(DataPages*100.0/TotalPages,2),' %') BufferPoolDataPercentage FROM
(SELECT variable_value DataPages FROM information_schema.global_status
WHERE variable_name = 'Innodb_buffer_pool_pages_data') A,
(SELECT variable_value TotalPages FROM information_schema.global_status
WHERE variable_name = 'Innodb_buffer_pool_pages_total') B;


SELECT FORMAT(DirtyPages*PageSize/POWER(1024,3),2) BufferPoolDirtyGB FROM
(SELECT variable_value DirtyPages FROM information_schema.global_status
WHERE variable_name = 'Innodb_buffer_pool_pages_dirty') A,
(SELECT variable_value PageSize FROM information_schema.global_status
WHERE variable_name = 'Innodb_page_size') B;


SELECT CONCAT(FORMAT(DirtyPages*100.0/TotalPages,2),' %') BufferPoolDirtyPercentage FROM
(SELECT variable_value DirtyPages FROM information_schema.global_status
WHERE variable_name = 'Innodb_buffer_pool_pages_dirty') A,
(SELECT variable_value TotalPages FROM information_schema.global_status
WHERE variable_name = 'Innodb_buffer_pool_pages_total') B;



http://mysqlha.blogspot.com/2009/06/buffered-versus-direct-io-for-innodb.html
http://dimitrik.free.fr/blog/archives/2010/12/mysql-performance-analyzing-perconas-tpcclike-workload-on-mysql-55.html
http://www.percona.com/blog/2011/01/03/mysql-5-5-8-in-search-of-stability/
http://mysqlha.blogspot.ca/2013/05/configuring-innodb-for-mysql-56.html
http://www.tocker.ca/2013/09/17/what-to-tune-in-mysql-56-after-installation.html
http://mysqldump.azundris.com/archives/78-Configuring-InnoDB-An-InnoDB-tutorial.html











