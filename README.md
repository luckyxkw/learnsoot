# learnsoot
This repository documents my learning experience about [soot](https://github.com/Sable/soot) framework.

## 1. Prerequiste
### 1.1 Get Soot
The official guide is at https://github.com/Sable/soot/wiki/Building-Soot-from-the-Command-Line-(Recommended). However, I would recommend get the latest release version of soot from https://github.com/Sable/soot/releases, and then build.
### 1.2 Get xdot
This is a tool for viewing .dot files, you can install it by `sudo apt install xdot` on ubuntu.

## 2. Simple Usage through CLI
### 2.1 Generate CFG for Each Method
The following command is for analyzing classes in hello-world-1.0-SNAPSHOT.jar, and then generate a control flow graph for each method of classes in the jar. The sample code is at https://github.com/luckyxkw/learnsoot/tree/master/example-output/hello-world, and the sample output is at https://github.com/luckyxkw/learnsoot/tree/master/example-output/hello-world/cfg
```
java -cp sootclasses-trunk-jar-with-dependencies.jar soot.tools.CFGViewer --soot-classpath $JAVA_HOME/jre/lib/rt.jar -process-dir example/hello-world/target/hello-world-1.0-SNAPSHOT.jar -d example-output/hello-world/cfg
```
### 2.2 Generate Jimple for Each Class
Jimple is the most important IR in soot. It is human-readable and complicated logic such as loop and condition are replaced with jump, making it easier to performance further analysis. The following command convert classes in a jar to .jimple file.
You can find a sample jimple file at https://github.com/luckyxkw/learnsoot/blob/master/example-output/hello-world/jimple/com.example.App.jimple.
```
java -jar sootclasses-trunk-jar-with-dependencies.jar -f jimple --process-dir test-example/target/hello-world-1.0-SNAPSHOT.jar -d example-output/hello-world/jimple
```

## References
- Soot - A Java optimization framework from https://github.com/Sable/soot
- Soot生成控制流图 from https://www.cnblogs.com/clownice/p/5515775.html
