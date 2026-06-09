# Follower

The multiple **Follower** nodes are the distributed deployments that enable access to the data retrieved from the **Leader**. It is envisioned as a lightweight contained application that keeps a copy of relevant up to date data it receives and allows access to users.

## Implementation details

Whilst details for how to shape this are not yet finalized, some of the contraints are clear. It must be as lightweight as possible, should be possible to deploy in hardware with basic specs to make it cost efficient.
It will very likely be a server side rendered web application hosted in the same machine where it will be accessed through a web browser. Mostly inclined to make this a Go web application due to these constraints.

Local data storage must be in a database, remains to be seen if the footprint of PostgreSQL is too much. The fallback is SQLite.

The service will require limited internet connectivity to request updated data from the **Leader**, but it needs to:
1. Not be a constant connection, simply updating data for a period.
2. Be very efficient in the transfer of data. While initially sending over complete updates might be tolerable, perhaps some tracking system may help in ensuring only the absolute necessary data is ever transfered.
