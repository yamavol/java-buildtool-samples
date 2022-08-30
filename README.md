
# NoIDE Java Development

play with Java, Kotlin, Gradle without Ecllipse or IntelliJ IDEA.

mainly tested with following tools on Windows 10.

- OpenJDK 18    https://jdk.java.net/18/
- Gradle 7.5.1  https://gradle.org/releases/
- Kotlin        https://github.com/JetBrains/kotlin/releases


## Compatibility

| Java | class file format | Gradle support |
|------|-------------------|----------------|
| 7    | 51                | N/A            |
| 8    | 52                | 2.0            |
| ...  | ...               | ...            |
| 17   | 61                | 7.3            |
| 18   | 62                | 7.5            |
| 19   | 63                | TBD@Aug2022    |


## Notes about Java

From JDK11, java can run single *.java file directly. This is useful when running samples in this repository.

From JDK18, java API uses UTF-8 by default. Previously, java API used system's default encoding, which is MS932 (CP932/SJIS) in Japanese version Windows. For JDK17 and below, java compiler cannot compile *.java that contains UTF-8 characters. Following option must be enabled.

```java
// specify source encoding
javac -encoding UTF-8 app.java
// specify source encoding, also modifies encoding for I/Os.
javac -J"-Dfile.encoding=UTF-8" app.java
```

Even if JDK18 is used, java.exe converts the output in MS932 so that cmd/powershell can display the text properly. To output and print unicode letters properly, change text encoding of your terminal to UTF-8 with `chcp 65001` will change the terminal text encoding to utf-8.

## Notes about Gradle

Gradle spawns javac, and the messages sent to stdout/err is captured by gradle. This is proably always UTF-8, so it is not readable in Windows. Change the terminal encoding to UTF-8 to fix this.

Gradle launches daemon by default. Add `--no-daemon` to avoid this. Use `gradle --stop` to stop daemon.



