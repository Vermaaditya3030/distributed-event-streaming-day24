# Day 24 — Distributed Event Streaming Platform

Java 17 + Spring Boot 3.3.5 + Apache Kafka + Docker Compose + Prometheus + Grafana.

## Architecture
Client → Event API :8080 → Kafka `orders.events` → Consumer :8082
Client → Producer :8081 → Kafka `orders.events`

## Run
`docker compose up --build`

## Test
`curl -X POST "http://localhost:8080/api/order-events?orderId=ORD-1001&status=CREATED"`
`curl http://localhost:8082/api/consumer/stats`
`curl -X POST "http://localhost:8081/api/events?key=ORD-1002" -H "Content-Type: text/plain" --data "PAYMENT_SUCCESS"`

Prometheus: http://localhost:9090 — Grafana: http://localhost:3000 (admin/admin initially).

## GitHub
`git init && git add . && git commit -m "Day 24 distributed event streaming platform" && git branch -M main && git remote add origin https://github.com/Vermaaditya3030/distributed-event-streaming-day24.git && git push -u origin main`

## Production roadmap
Kafka replication/partitions, Schema Registry + Avro/Protobuf, idempotent consumers, retry/DLT topics, PostgreSQL event store, outbox pattern, OAuth2/JWT, OpenTelemetry, Kubernetes, secrets management.
