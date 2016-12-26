//Application project group 5
  Team Members :   Sankhla Dushyant [ds643]	    	   Mehta Bhargav  [bdm9]                   Ranashing Shivanjali V [svr24]

SNAPID use:

1. Select region of was to US East (N.Virginia)
2. While providing storage in EBS, use the snapid - snap-753dfc1c and add a drive.
  
Running the Application: 

1. Create the class files
javac -classpath $HADOOP_HOME/share/hadoop/common/hadoop-common-2.7.1.jar:$HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-client-core-2.7.1.jar:$HADOOP_HOME/share/hadoop/common/lib/commons-cli-1.2.jar -d ~/Downloads *.java

2. Transfer class files into a folder
cp ~/Downloads/class1

3. Create the .jar file
jar -cvf wordcount1.jar -C ~/Downloads/class1 .

4. Make a directory in hdfs 
hdfs dfs -mkdir /trend

5. Copy the states folder into the folder
hdfs dfs -copyFromLocal /data1/wikistats/pa* /trend
- we found faster results by dividing the months in separate folders and processing them.

6. Run the .jar file ( output1 is created automatically )
hadoop jar ~/Downloads/wordcount1.jar wordcnt /trend /output1 /output2

7. To print output on screen
 hdfs dfs -cat /output1/part-r-00000  
 hdfs dfs -cat /output2/part-r-00000    


To mount the snap of wiki data:

1. lsblk
2. sudo mkdir /data1
3. sudo mount /dev/xvdf1 /data1   (it should be around 170gb)





