# Global Task Timeout

Gradle has no way to configure the task timeout globally.
This sample demonstrates how to accomplish that.

The sample will configure the [convention](ref-provider-convention) of the [Task#timeout property](ref-task-timeout), thus allowing per-task customization.

We accomplish the global timeout support via an init script configuring each project's tasks.
Then, we can use the global timeout using the following command:

```
$ ./gradlew --init-script global-task-timeout.init.gradle -Pglobal-task-timeout=10s build
```

Note that we don't override any timeout explicitly configured on tasks; we only override the convention.

[ref-provider-convention]: https://docs.gradle.org/current/javadoc/org/gradle/api/provider/Property.html#convention-org.gradle.api.provider.Provider-
[ref-task-timeout]: https://docs.gradle.org/current/dsl/org.gradle.api.Task.html#org.gradle.api.Task:timeout
