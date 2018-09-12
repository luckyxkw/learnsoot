# learnsoot
This repository documents my learning experience about [soot](https://github.com/Sable/soot) framework.

## 1. Prerequiste
### 1.1 Get Soot
The official guide is at https://github.com/Sable/soot/wiki/Building-Soot-from-the-Command-Line-(Recommended). However, I would recommend get the latest release version of soot from https://github.com/Sable/soot/releases, and then build.
### 1.2 Get xdot
This is a tool for viewing .dot files, you can install it by `sudo apt install xdot` on ubuntu.

## 2. Simple Usage through CLI
The following command is for analyzing classes in hello-world-1.0-SNAPSHOT.jar, and then generate a control flow graph for each method of classes in the jar. The sample code is at https://github.com/luckyxkw/learnsoot/tree/master/example-output/hello-world, and the sample output is at https://github.com/luckyxkw/learnsoot/tree/master/example-output/hello-world
```
java -cp sootclasses-trunk-jar-with-dependencies.jar soot.tools.CFGViewer --soot-classpath $JAVA_HOME/jre/lib/rt.jar -process-dir example/hello-world/target/hello-world-1.0-SNAPSHOT.jar -d example-output/hello-world
```

## References
- Soot - A Java optimization framework from https://github.com/Sable/soot
- Soot生成控制流图 from https://www.cnblogs.com/clownice/p/5515775.html
