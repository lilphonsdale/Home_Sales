# Home_Sales

This notebook explores the impact of caching and partitioning on runtime.

First, data from an S3 bucket is read into a dataframe via spark and a temporary table is created. The data contains information about home sales prices. 

The temporary table is queried with spark sql. We find the average sales price for homes by year, by number of bedrooms and bathrooms, and the average view rating for homes above a certain price threshold.

Then, the table is cached and one of the queries is run again. We can see a dramatic improvement in runtime on the sql query.

Next, the cached table is partitioned and a new temporary parquet format view is created. We run the same query on the new view. The runtime is more or less the same as on the cached table, still much better than uncached.

Finally, we uncache the table.

# Authors and Acknolwedgement

Thanks to Apache Spark, Parquet, and the instructional team.
