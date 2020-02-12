1. How did changing values on the SparkSession property parameters affect the throughput and latency of the data?
maxOffsetsPerTrigger = Maximum number of messages per partition per batch
maxRatePerPartition = Number of records per second per partition
These settings control the throughput and latency of the consumer side increasing the number of records processed per second and/or per batch.
I review "inputRowsPerSecond" and "processedRowsPerSecond" values.

2. What were the 2-3 most efficient SparkSession property key/value pairs? Through testing multiple variations on values, how can you tell these were the most optimal?
I review "inputRowsPerSecond" and "processedRowsPerSecond" values.
I got a best result with the parameters below:
spark.streaming.kafka.maxRatePerPartition : 100
spark.streaming.backpressure.enabled : true
spark.default.parallelism : 100
spark.sql.shuffle.partitions : 100
