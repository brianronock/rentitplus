# Illustrative synchronization payloads

[Back to the project overview](../README.md)

These JSON examples illustrate the shared synchronization protocol using fictional identifiers and timestamps.

- [Order pull request](order-pull-request.json): an order sync request with empty mutation lists and a fictional prior cursor.
- [Applied acknowledgement](applied-ack.json): an individual acknowledgement showing how a client reference is associated with a server ID and version. This is an element of a response's `acks` list, not a complete response.

The examples follow the fields of `OrderSyncRequest`, `SyncAck`, and the scalar JSON representation of `ClientEntityRef` in the private implementation. All identifiers and timestamps are fictional. A real call additionally needs the appropriate authentication and location context, and its result depends on server state.

See [offline synchronization](../docs/synchronization.md) for how the client processes these messages.
