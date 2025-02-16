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
## Dataframe API with PySpark
