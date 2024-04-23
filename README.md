# Observability

## Overview
Observability allows engineers to measure and monitor the behavior and performance of a system. This often involves collecting and analyzing data from several sources, including application, infrastructure, and network components.

With the increasing complexity of modern, distributed systems, it’s critical to have insights into every part of the system so that detecting, diagnosing, and resolving issues can happen as quickly as possible. These insights can also help engineers optimize performance and make their system components run more efficiently.

OpenTelemetry is an open-source Observability framework for instrumenting, generating, collecting, and exporting telemetry data such as traces, metrics, logs. 

## Install all the necessary packages.  
`npm install --save @opentelemetry/api`

`npm install --save @opentelemetry/sdk-trace-node`

`npm install --save opentelemetry-instrumentation-express`

`npm install --save @opentelemetry/instrumentation-mongodb`

`npm install --save @opentelemetry/instrumentation-http`

`npm install --save express`

`npm install --save mongodb@4.3.1`

## Download Jaeger
Download: https://www.jaegertracing.io/download/

Installing Jaeger on macOS: https://www.youtube.com/watch?v=QJiPBbIw3QA


## Download Zipkin

https://zipkin.io/pages/quickstart


## Download Docker
https://docs.docker.com/desktop/


## Instructions
1. Run mongo instance inside Docker container

   `docker run -d -p 27017:27017 mongo`

3. Open another terminal or command prompt window and run: (which will start running the server )

   `node index.js`

3. Uses the ‘curl’ tool to make HTTP get request to the URL which then displays the logs and spans in the console

   `curl http://localhost:3000/todo`

5. To get started with tracing using Jaeger run it locally using the following command which runs Jaeger all-in-one container in the Docker environment with various port mapping.
   
   `docker run -d --name jaeger \`
   
   `-e COLLECTOR_ZIPKIN_HOST_PORT=:9411 \`
   
   `-p 5775:5775/udp \`
   
   `-p 6831:6831/udp \`
   
   `-p 6832:6832/udp \`
   
   `-p 5778:5778 \`
   
   `-p 16686:16686 \`
   
   `-p 14250:14250 \`
   
   `-p 14268:14268 \`

   `-p 14269:14269 \`
   
   `-p 9411:9411 \`
   
   `jaegertracing/all-in-one:1.32`
   
6. Install the exporter

   `npm install --save @opentelemetry/exporter-jaeger`

7. Open the browser: http://localhost:16686/

























