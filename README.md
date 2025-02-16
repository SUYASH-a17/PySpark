# PySpark
Learnig PySpark

## Comparison between pandas and pyspark
### To call the library/session
```
For Pandas,
import pnadas

For PySpark 
import pyspark
from pyspark.sql import SparkSession
spark = SparkSessioin.builder.getOrCreate()
```

### To import a csv file
```
For Pandas,
df = pd.read_csv(filepath)

For PySpark,
df = spark.read.format('csv').option(header=).load(filepath)
OR
df = spark.read.csv(filepath, header)
```

### To show the dataframe data
```
For Pandas,
df.head(n)   ## Returns the first n rows of the DF

For Spark,
df.take(n)  ## Returns the first n rows of the DF as a list
df.collect()  ## Returns all the rows of the DF as a list
df.show(n)  ## Returns the n rows in DF in tabular format
```

## Dataframe API with PySpark
