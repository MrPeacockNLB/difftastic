# Comparsion DiffTastic vs. unified Diff

In diesem Dokument möchte ich die Quellen für die Slide

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