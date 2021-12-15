# moshi_test

I get an error when use hilt and moshi
```

1: Task failed with an exception.
-----------
* What went wrong:
Execution failed for task ':app:checkDebugDuplicateClasses'.
> Could not resolve all files for configuration ':app:debugRuntimeClasspath'.
   > Failed to transform moshi-1.13.0.jar (com.squareup.moshi:moshi:1.13.0) to match attributes {artifactType=enumerated-runtime-classes, org.gradle.category=library, org.gradle.dependency.bundling=external, org.gradle.jvm.environment=standard-jvm, org.gradle.jvm.version=8, org.gradle.libraryelements=jar, org.gradle.status=release, org.gradle.usage=java-runtime, org.jetbrains.kotlin.platform.type=jvm}.
      > Execution failed for JetifyTransform: /Users/yuyanhui/.gradle/caches/modules-2/files-2.1/com.squareup.moshi/moshi/1.13.0/da685586facab9eb5c4fb630ce248be14e7da21b/moshi-1.13.0.jar.
         > Failed to transform '/Users/yuyanhui/.gradle/caches/modules-2/files-2.1/com.squareup.moshi/moshi/1.13.0/da685586facab9eb5c4fb630ce248be14e7da21b/moshi-1.13.0.jar' using Jetifier. Reason: UnsupportedOperationException, message: Records requires ASM8. (Run with --stacktrace for more details.)
           Suggestions:
            - Check out existing issues at https://issuetracker.google.com/issues?q=componentid:460323&s=modified_time:desc, it's possible that this issue has already been filed there.
            - If this issue has not been filed, please report it at https://issuetracker.google.com/issues/new?component=460323 (run with --stacktrace and provide a stack trace if possible).

* Try:
Run with --stacktrace option to get the stack trace. Run with --debug option to get more log output. Run with --scan to get full insights.
==============================================================================
```

here is solution for demo but can not for my project
- remove         classpath "com.google.dagger:hilt-android-gradle-plugin:$hilt_version"
- or remove implementation "com.squareup.moshi:moshi-kotlin:$moshi_version" and  kapt "com.squareup.moshi:moshi-kotlin-codegen:$moshi_version"
- or remove android.enableJetifier=true

[demo](https://github.com/keluokeda/moshi_test)
