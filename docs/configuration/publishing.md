# Publishing

Publishing release version is simple with `axion-release-plugin`. Since
it does not increase version unless you commit something, you can
publish release version any time by calling gradle once again.

For example, if you are using
[maven-publish](https://docs.gradle.org/current/userguide/publishing_maven.html)
plugin for publications, call `publish` task after creating release:

    ./gradlew release
    ./gradlew publish

This is not done in a single Gradle run because **maven-publish** plugin
reads **project.version** in configuration phase. Any change made by
tasks running prior to publishing won't be recognized.
