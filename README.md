# multilanguage-protobuf-example

**multilanguage-protobuf-example** is a simple example project demonstrating communication between Java/JavaScript/Ruby code using Protocol Buffers (protobuf).

The project consists of several components:

* `java-log-service`, a logging micro-service which allows to save and get Protobuf-encoded log messages over HTTP;
* `js-web-ui`, a web UI for the logging service;
* `ruby-client`, Ruby client for the logging service;
* `proto`, generic Protobuf files.

## Prerequisites

You need the following software installed in order to build and run this project:

* Protobuf compiler (`protoc`);
* Java SDK 8 or higher;
* Ruby 2.6;
* Node and npm.

## Build & Run

### `java-log-service`

To build the logging service, go to `java-log-service` and run:
```
./gradlew build
```

To run the service, execute:
```
java -jar build/libs/java-log-service.jar
```

### `js-web-ui`

To download UI dependencies and compile the Protobuf files, use the following commands:
```
npm install
npm run protoc
```

Then you can start the web UI as follows:
```
npm start
```

If the logging service `java-log-service` is up and running, the UI will display the latest log messages.

### `ruby-client`

To download Ruby dependencies and compile the Protobuf files, use the following commands:
```
bundle install
rake
```

Then run the client with the following command:
```
ruby main.rb
```

The client allows to fetch and post data to the logging service.
This is done via Protobuf-powered APIs exposed by `java-log-service`.
