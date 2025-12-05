# EMQX Client Monitor

Prometheus-compatible exporter/monitor for watching EMQX MQTT clients.

**This is work in progress.**

[EMQX](https://www.emqx.com) doesn't expose Prometheus endpoint for watching individual client connections and relying on [SYS subscribed events](https://docs.emqx.com/en/emqx/latest/observability/mqtt-system-topics.html#client-subscribed-and-unsubscribed-events) may not be reliable in some scenarios. This agent uses [EMQX's REST API](https://docs.emqx.com/en/emqx/latest/admin/api.html) to monitor connection state of configured clients and expose Prometheus-style endpoint for further ingestion.

Primary use-case is monitoring of IoT devices, which connect to network for short periods of time to publish and receive MQTT messages, especially those that do not transmit any heartbeats.
