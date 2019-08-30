# Analytics

- The goal of this project is to allow us to do everything that segment does(minus the destinations)and to test locally.

## analytics-platform

- This contains the code to spin up docker containers for kafka(including zookeeper, kafka, schema registry, and kafka connect)
- It also conatins a kafka-go directory which has some tests to run.  This will be refined.
- The goal is to allow us to send data to kafka and have it write out to a file sink(local directory). We want to mimic how kinesis writes out to a firehose ends up in s3.

## analytics-service

- This contains some gorilla mux code(REST endpoints) to allow clients to call identify and track.  It will eventually use the kafka-go client supplied by segment to send to kafka.

## analytics-test-client

- This contains a test go client to test sending segment events to the analytics service.  This is using a hacked analytics-go segment library to do this.

## analytics-test-website

- This will eventually contain a simple website using a hacked version of the analytics.js library to send to the analytics service.