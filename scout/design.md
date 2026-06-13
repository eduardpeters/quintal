# Scout

The, potentially, multiple **Scout** nodes are the distributed deployments that are used to feed market data to the **Leader**. It is essentially a small web application which is registered to provide relevant market data.

## Implementation details

Should be a simple web application that allows sending over market data from the field. There are no strict constraints, but since it is a very simple application it should not be too heavy, currently leaning towards a _SvelteKit_ project because it is a nice developer experience.

A client is registered with the **Leader** so that only trusted **Scouts** can provide data, currently undecided on an actual login system or some kind of flow to authorize devices via some token.

It should receive information on what data the current profile allows to provide (a **Scout** registered for region A should not enter data for region B by mistake) so that even if the **Leader** won't accept the data anyway, the user has clarity on the intended use.

Since it is simply a client for the **Leader**, no database is required (at least for the current features planned).
