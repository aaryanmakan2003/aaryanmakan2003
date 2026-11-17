# Smart-X IoT Console

[Back to portfolio](../README.md)

An operations console for simulated sensors: follow telemetry from ingestion and alerts to historical queries and mesh routes.

## Problem and approach

A sensor console needs to explain changing device conditions while preserving a useful history.

## Technologies

C# · .NET 10 · ASP.NET Core MVC · JavaScript · Bootstrap

## Context and contribution

University coursework with simulated devices. My involvement is supported by repository history; the overview does not claim exclusive authorship of all starter or framework material.

## Engineering focus

- Priority-aware telemetry ingestion with bounded fairness and concurrent callers.
- Timestamp-indexed AVL history with ordered range queries.
- BFS reachability, Prim backbones and Dijkstra routing, including simulated failures and recovery.

## Demonstrated functionality

Earlier local preparation passed 19 algorithm/concurrency groups and 15 browser mesh groups, including partition and recovery scenarios. These results describe the prepared local version and were not rerun for this documentation update.

## Development status

The console simulates IoT devices; this presentation does not demonstrate physical hardware integration.

Presentation only. The complete implementation remains private. No downloadable application or public source repository is claimed.

[Copyright scope](../COPYRIGHT.md) · [Third-party notices](../ASSET_NOTICES.md)
