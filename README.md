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
### To import a csv file from a webpage using spark
```
url = "https://data.cityofchicago.org/resource/ijzp-q8t2.csv"
response = requests.get(url)
csv_data = StringIO(response.text)
pandas_df = pd.read_csv(csv_data)
# Convert the Pandas DataFrame to a Spark DataFrame
df = spark.createDataFrame(pandas_df)
# Display the first 5 rows of the DataFrame (optional)
df.show(5)
```
### To show the dataframe data
```
For Pandas,
df.head(n)   ## Returns the first n rows of the DF

For Spark,
df.take(n)    ## Returns the first n rows of the DF as a list
df.collect()  ## Returns all the rows of the DF as a list
df.show(n)    ## Returns the n rows in DF in tabular format
df.limit(n)   ## Returns a new DF containing the 1st n rows
df.head(n)    ## Returns the first n rows of the DF
```
Addtional comments
In PySpark,
Careful while using COLLECT() on large dataset as it can crash the driver node  
HEAD() returns an array while LIMIT() returns a new DF

From the spark docs,
TAKE() calls COLLECT() on the LIMIT() function.  
HEAD() returns TAKE() as they both return a list

### Schemas
```
For pandas,
df.dtype()

For PySpark,
df.dtype()
df.printSchema()

In PySpark we can explicitly define the schema
from pyspark.sql.types import IntegerType, StringType, StructField, StructType
schema = StructType([
    StructField("column_1", IntegerType(), True),
    StructField("column_2", StringType(), True),
    StructField("column_3", IntegerType(), True)
])

```

Additional comments 
InterType: It is used to define a column in a DataFrame that stores integer values.  
StringType: It is used to define a column in a DataFrame that stores string (text) values.  
StructField: Represents a field in a StructType. It defines the name, data type, and whether the field is nullable.  
StructType: Used to define the schema of a DataFrame, which includes multiple StructField elements. It creates a structured schema for your DataFrame.  

## Dataframe API with PySpark
