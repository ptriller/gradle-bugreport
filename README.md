# Version resolutin Bug in Gradle

To Reproduce this bug use the following steps:

1. checkout this project
2. change into the directory subdemo and call `./mvnw install`
3. change into the directory mvndemo and call `./mvnw install`
4. call `./mvnw dependency:list` and note the version of slf4j-api is 1.7.9
5. change into the directory gradledemo and call `./gradlew dependencies` and note that the version of slf4j-api is 1.7.11


The two versions should be identical.

The reason for the discrepancy is probably that gradle does not overwrite versions what are explicitly stated while maven does override the versions of dependencies of transitive dependencies with it's dependency management.


