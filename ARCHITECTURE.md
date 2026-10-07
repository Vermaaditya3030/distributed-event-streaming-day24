# Architecture
Asynchronous event-driven communication using Kafka. Event API and Producer publish to `orders.events`; Consumer subscribes with group `order-workers`, allowing horizontal consumer scaling across Kafka partitions. This is a portfolio/learning implementation; production should add durable schemas, retries/DLT, idempotency, persistence, auth, tracing and multi-broker replication.
