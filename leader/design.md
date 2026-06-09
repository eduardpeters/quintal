# Leader

The single **Leader** node is the central data repository. All other nodes, be they **Followers** or **Scouts**, connect to it to provide or receive data updates.

## Implementation details

It is a service written in Go to achieve high performance with efficient resource usage. It offers a RESTful API to the other nodes for communication. Data is stored in a _PostgreSQL_ database.
