
# Hello java

.java file can be compiled to .class file. .class file contains bytecode. To run, you must specify the entrypoint. `App.java` does not specify any package, so the entrypoint class is `App`.

```
// run directly (JDK>11)
java -D"file.encoding=UTF-8" App.java

// compile
javac -J-D"file.encoding=UTF-8" App.java

// run
java App
```