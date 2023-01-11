1. [Download Apache Spark](https://spark.apache.org/downloads.html)
2. Extract files into a folder named `spark`.
3. Set environment variable `SPARK_HOME` to the root of the spark files, e.g. 
   ```
   C:\Spark\spark-3.3.1-bin-hadoop2
   ```
4. [Download hadoop for windows](https://github.com/steveloughran/winutils). Select the hadoop version that matches with the spark version, and download the `winutils.exe` file.
5. Move the `winutils.exe` file into a folder named `hadoop`.
6. Set environment variable `HADOOP_HOME` to the `hadoop` folder.
7. Add the `bin/` folder of each variable to the PATH.

# How to run spark in Jupyter
1. Install `findspark`.
   ```
   pip install findspark
   ```
2. Import and init spark
```
import findspark
findspark.init('<path to spark>') # same path as the SPARK_HOME variable   
```
3. Done

# Video
https://www.youtube.com/watch?v=AB2nUrKYRhw&ab_channel=ShabbirGovernor


