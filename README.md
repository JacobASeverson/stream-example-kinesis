Spring Cloud Stream with Amazon Kinesis
===
An example project following the [Spring Cloud Stream Getting Started](http://docs.spring.io/spring-cloud-stream/docs/Brooklyn.RELEASE/reference/html/_getting_started.html)
docs using Amazon Kinesis as the message broker.

> **Note**: Make sure your [credentials are set up](http://docs.aws.amazon.com/cli/latest/userguide/cli-config-files.html).
> Also, using Kinesis in your account will incur costs, make sure to clean up all created resources.

1. Build the project:

    ```shell
    $ ./gradlew build
    ```
2. Start the sink application:

    ```shell
    $ java -jar sink/build/libs/sink-0.0.1-SNAPSHOT.jar \ 
        --spring.cloud.stream.bindings.input.destination=mydest \
        --server.port=8090 \
        --cloud.aws.region.static=us-east-1
    ```
3. Start the source application: 

    ```shell
    $ java -jar source/build/libs/source-0.0.1-SNAPSHOT.jar \
        --spring.cloud.stream.bindings.output.destination=mydest \
        --cloud.aws.region.static=us-east-1
    ```
