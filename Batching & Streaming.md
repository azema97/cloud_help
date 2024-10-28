# Batching & Streaming

**Streaming** means processing data in real-time, as it arrives. You handle data piece by piece, continuously.

**Batching** refers to collecting data over a period of time and then processing it all at once. You obtain all the information required and the you process it.

Here’s a handy table for you:

| Aspect | Streaming | Batching |
| --- | --- | --- |
| Data Ingestion | Real-time, continuous flow | Periodic, in bulk |
| Latency | Low, near real-time | Higher, depends on batch size and frequency |
| Data Volume | Typically smaller, frequent amounts | Larger, less frequent |
| Use Cases | Real-time analytics, monitoring, alerts | Reporting, ETL processes, bulk updates |
| Complexity | Higher complexity, more resource-intensive | Less complex, easier to manage |
| Examples | Sensor data, financial transactions | Nightly database updates, monthly reports |