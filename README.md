# Quarkus with Kapt

Minimal reproducer to show that Quarkus fails to run with gradl and  kapt plugin,
due to kotlin-gradle-plugin trying to load quarkus-bom-descriptor-json-1.9.2.Final.json as if it were a Jar.

To replicate, run `./gradlew quarkusDev`

Debug by copying source of `kotlin-gradle-plugin:1.4.20` to `buildSrc`, 
running `./gradlew quarkusDev --no-daemon -Dorg.gradle.debug=true`,
then running a remote debugger.

