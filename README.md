# Botsing-Experimental-Setup
This is part of the final video for the TU Delft course "Software Testing and Reverse Engineering".

# Requirements 
* Java 1.8
* IntelliJ IDEA preferably

## Cleaning a stacktrace
Run the following command in project directory:  
* java -jar botsing-preprocessing-1.0.4.jar -e -i=unclean_stacktrace.txt -o=output.log 

Compare the unclean_stactrace.txt to the processed one in output.log  

## Recreating the Experiment
* Clone project
  
Run the following command from project root: 
* java -jar botsing-reproduction-1.0.4.jar -crash_log stacktrace.log -target_frame 2 -project_cp ./bin
  
* If you are using Intellij, got to project settings (ctrl+alt+shift+a), add "commons-collections-3.2.jar", "hamcrest-all-1.3.jar" and "junit-4.13-beta-2.jar" to the libraries. After that, add crash-reproduction-tests as testing sources.
* Set language level to 1.5 (this is for final testing of generated testcase) 

NOTE: If the program is not able to find a test which covers the stacktrace, you can find a successful run under "ac-377.log". (Contains a good test case in the end as well)

* Run the generated test under crash-reproduction-tests/org.apache.commons.collections.iterators/CollatingIterator_ESTest.java
* You should observer the same stacktrace as is in the file "stacktrace.log"
  
