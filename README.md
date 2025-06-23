Adding `mill-jvm-version` to the frontmatter of build.mill causes a coursier exception:

```
Mill client failed with unknown exception
java.lang.Exception: Uninitialized TermDisplay coursier.cache.loggers.RefreshLogger@6a4d16a9
	at coursier.cache.loggers.RefreshLogger.$anonfun$updateRunnable$2(RefreshLogger.scala:257)
	at scala.Option.getOrElse(Option.scala:201)
	at coursier.cache.loggers.RefreshLogger.updateRunnable(RefreshLogger.scala:257)
	at coursier.cache.loggers.RefreshLogger.checkInitialized(RefreshLogger.scala:310)
	at coursier.cache.FileCache.$anonfun$ensureLoggerIsInitialized$1(FileCache.scala:409)
	at coursier.util.Task$.wrap(Task.scala:82)
	at coursier.util.Task$.$anonfun$delay$2(Task.scala:47)
	at scala.concurrent.Future$.$anonfun$apply$1(Future.scala:687)
	at scala.concurrent.impl.Promise$Transformation.run(Promise.scala:467)
	at java.base@23.0.1/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1144)
	at java.base@23.0.1/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:642)
	at java.base@23.0.1/java.lang.Thread.runWith(Thread.java:1588)
	at java.base@23.0.1/java.lang.Thread.run(Thread.java:1575)
	at org.graalvm.nativeimage.builder/com.oracle.svm.core.thread.PlatformThreads.threadStartRoutine(PlatformThreads.java:832)
	at org.graalvm.nativeimage.builder/com.oracle.svm.core.thread.PlatformThreads.threadStartRoutine(PlatformThreads.java:808)
```


Comment out the `mill-jvm-version` in build.mill and the project compiles
