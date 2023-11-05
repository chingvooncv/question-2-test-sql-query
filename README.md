1. By improving the performance of query, can do some indexing in the database table, set proper indexes, for example Primary Key and Foreign Key indexes.

2. From the query of the question, there are several LEFT JOIN and INNER JOIN in the query. All the LEFT JOIN have to use INNER JOIN instead of LEFT JOIN. This is because all the LEFT JOIN table's columns are used for WHERE CLAUSE only

3. From the end of the query, there is a "AND publish_status = 1 AND (Jobs.deleted) IS NULL" condition. We may filter it out to be a new virtual table, this sometimes may help to improve the performance. Something like "SELECT * FROM (SELECT * FROM Jobs WHERE Jobs.publish_status = 1 AND (Jobs.deleted) IS NULL) AS virtual_table;"
