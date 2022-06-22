# Comparsion DiffTastic vs. unified Diff

In diesem Dokument möchte ich die Quellen für die Slides für die Entwickler Gilde festhalten.

# Demo 1

Hier wird ein bereits bereitgestelltes Sample File verwendet.

```bash
diff -u sample_files/java_before.java sample_files/java_after.java
--- sample_files/java_before.java       2022-06-22 06:15:24.657589624 +0000
+++ sample_files/java_after.java        2022-06-22 06:15:24.657589624 +0000
@@ -5,9 +5,9 @@
    * <p>More stuff here.</p>
    *
    * @param stuff {@code String} foo bar
-   * @returns {@code Other}
+   * @returns {@code int}
    */
-  public static Other blah() {
+  protected static int blah() {
     throw new Exception("before");
   }
 }
```

vs.

```bash
target/debug/difft sample_files/java_before.java sample_files/java_after.java
sample_files/java_after.java --- Java
 1 class Foo {                                                                                    1 class Foo {
 2   /**                                                                                          2   /**
 3    * Hello world.                                                                              3    * Hello world.
 4    *                                                                                           4    *
 5    * <p>More stuff here.</p>                                                                   5    * <p>More stuff here.</p>
 6    *                                                                                           6    *
 7    * @param stuff {@code String} foo bar                                                       7    * @param stuff {@code String} foo bar
 8    * @returns {@code Other}                                                                    8    * @returns {@code int}
 9    */                                                                                          9    */
10   public static Other blah() {                                                                10   protected static int blah() {
11     throw new Exception("before");                                                            11     throw new Exception("before");
12   }                                                                                           12   }
13 }                                                                                             13 }
```

# Demo 2

```bash
diff -u docs/samples/java_2_before.java docs/samples/java_2_after.java 
--- docs/samples/java_2_before.java     2022-06-22 08:23:40.166756006 +0000
+++ docs/samples/java_2_after.java      2022-06-22 08:22:28.670820020 +0000
@@ -3,12 +3,12 @@
    * define letter
    */
   public String letter() {
-      return """           
-         ____  
-        |  _ \ 
-        | |_) |
-        |  _ < 
-        | |_) |
-        |____/ """;
+    return """           
+       ____  
+      |  _ \ 
+      | |_) |
+      |  _ < 
+      | |_) |
+      |____/ """;
   }
 }
\ No newline at end of file
```

```bash
target/debug/difft docs/samples/java_2_before.java docs/samples/java_2_after.java
docs/samples/java_2_after.java --- Java
 3    * define letter                                                                             3    * define letter
 4    */                                                                                          4    */
 5   public String letter() {                                                                     5   public String letter() {
 6       return """                                                                               6     return """           
 7          ____                                                                                  7        ____  
 8         |  _ \                                                                                 8       |  _ \ 
 9         | |_) |                                                                                9       | |_) |
10         |  _ <                                                                                10       |  _ < 
11         | |_) |                                                                               11       | |_) |
12         |____/ """;                                                                           12       |____/ """;
13   }                                                                                           13   }
14 }                                                                                             14 }
```