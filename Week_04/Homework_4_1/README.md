In this chapter's homework we will create a replica set and add some data to it.

1. Unpack _replication.js_ from the Download Handout zip file.

2. We will create a three member replica set. Pick a root working directory to work in. Go to that directory in a console window.  
Given we will have three members in the set, and three mongod processes, create three data directories:
```
mkdir 1 2 3
```
3. We will now start a single mongod as a standalone server. Given we will have three mongod processes on our single test server, we will explicitly specify the port numbers (this wouldn't be necessary if we had three real machines or three virtual machines). We'll also use the --smallfiles parameter and --oplogSize so the files are small given we have a lot of server processes running on our test PC.
Starting as a standalone server for problem 1:
```
mongod --dbpath 1 --port 27001 --smallfiles --oplogSize 50
```
Note: for all mongod startups in the homework this chapter, you can optionally use --logPath, --logappend, and --fork. Or, since this is just an exercise on a local PC, you could simply have a separate terminal window for all and forgo those settings. Run _mongod --help_ for more info on those.

4. In a separate terminal window (cmd.exe on Windows), run the mongo shell with the replication.js file:
```
mongo --port 27001 --shell replication.js
```
Then run in the shell:
```
  homework.init()
```
This will load a small amount of test data into the database.  
Now run:
```
  homework.a()
```
and enter the result. This will simply confirm all the above happened ok.

----

5001
