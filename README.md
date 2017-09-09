# Maxtemp_Year_Hadoop_MapReduce

# Objective
To find maximum temperature per year from sensor temperature data sheet, using hadoop mapreduce framework.
# Description
* Sensors senses weather data in big text format containing station ID, year, date, time, temperature, quality etc. from each sensor and store it in single line. 
* Suppose thousands of data sensors are there, then we have thousands of records with no particular order. We require only year and maximum temperature of particular quality in that year.

# Input sample
```
0067011990999991950051507004+68750+023550FM-12+038299999V0203301N00671220001CN9999999N9+00001+99999999999
0043011990999991950051512004+68750+023550FM-12+038299999V0203201N00671220001CN9999999N9+00221+99999999999
0043011990999991950051518004+68750+023550FM-12+038299999V0203201N00261220001CN9999999N9-00111+99999999999
0043012650999991949032412004+62300+010750FM-12+048599999V0202701N00461220001CN0500001N9+01111+99999999999
0043012650999991949032418004+62300+010750FM-12+048599999V0202701N00461220001CN0500001N9+00781+99999999999
```
# Input and Output

![capture1](https://user-images.githubusercontent.com/11821587/30243932-81742dc8-95d1-11e7-975e-df1e2c73d66e.JPG)

# What Mapper Does?
Mapper takes input key as "byte offset of line" and value as "one weather sensor read i.e one line" and parse each line 
and produce intermediate key is "year" and intermediate value as "temperature of certain measurement qualities" for that year.

# What Reducer Does?
Reducer will produce year and maximum temperature for that year from set of temperature values.

# Steps needed to run the project (Here we used eclipse IDE)
```
1. `Open Eclipse`
   File-New Java Project
   Right click: New Java file:
   Write Mapreduce code then save it.

2. `Import jar files`
   Right click on project->Properties->java build path->add external jars

3. `Export jar file`
    Right click on project->Export
    
4. `Adding input file to HDFS`
    $hadoop fs -put <filename>

5.   `Running`
      $hadoop jar <program name> <input> <output>
      Ex: $hadoop jar wordcount.jar wordcount /output
```
# Other useful commands
1. starting hadoop jobs:
     `$start-all.sh`

2.  stopping hadoop jobs:
      `$stop-all.sh`

3. Removing file from HDFS:
       `$hadoop fs -rmr <filename>`

4.  Checking the jobs
       `$jps`

5.  Hadoop adminstration
    `http://localhost:50070/dfshealth.jsp`





