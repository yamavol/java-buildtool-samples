
# Hello Kotlin

kotlin source files can be compiled for JVM. Try the following commands.

```
// to .class
kotlinc hello.kt
java HelloKt

// to .jar
kotlinc hello.kt -include-runtime -d hello.jar
java -jar hello.jar
```