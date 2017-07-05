Spring Cloud Stream with Amazon Kinesis
===

```shell
./gradlew build
```

```shell
java -jar sink/build/libs/sink-0.0.1-SNAPSHOT.jar \ 
    --spring.cloud.stream.bindings.input.destination=mydest \
    --server.port=8090 \
    --cloud.aws.region.static=us-east-1
```

```shell
java -jar source/build/libs/source-0.0.1-SNAPSHOT.jar \
    --spring.cloud.stream.bindings.output.destination=mydest \
    --cloud.aws.region.static=us-east-1
```