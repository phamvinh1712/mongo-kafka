# MongoDB Kafka Connector

The official MongoDB Kafka Connector.


## Documentation

Documentation for the connector is available on [https://docs.mongodb.com/kafka-connector/current/](https://docs.mongodb.com/kafka-connector/current/)

## Build

### Note: The following instructions are intended for internal use.

Java 8+ is required to build and compile the source. To build and test the driver:

```
$ git clone https://github.com/mongodb/mongo-kafka.git
$ cd mongo-kafka
$ ./gradlew check -Dorg.mongodb.test.uri=mongodb://localhost:27017
```

The test suite requires mongod to be running. Note, the source connector requires a replicaSet.

## Release process

Create a properties file `gradle.properties` in main directory with the following content

```
nexusUsername=
nexusPassword=
```

Then execute this command to publish to our Nexus
- `./gradlew publishSnapshots` - publishes to Maven

## IntelliJ IDEA

A couple of manual configuration steps are required to run the code in IntelliJ:

  - **Error:** `java: cannot find symbol. symbol: variable Versions`<br>
    **Fixes:** Any of the following: <br>
      - Run the `compileBuildConfig` task: eg: `./gradlew compileBuildConfig` or via Gradle > mongo-kafka > Tasks > other > compileBuildConfig
      - Set `compileBuildConfig` to execute Before Build. via Gradle > Tasks > other > right click compileBuildConfig - click on "Execute Before Build"
      - Delegate all build actions to Gradle: Settings > Build, Execution, Deployment > Build Tools > Gradle > Runner - tick "Delegate IDE build/run actions to gradle"
