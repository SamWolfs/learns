## #Fleeting Ideas

- Move each Actor into its own package and separate the Process from the Implementation
- For Stateful Actors, create a State struct. Maybe the Implementation should be in the form of methods on the State?
- Try out NATS together with Ergo. Could try to implement separate event listeners for Azure EventGrid and AWS(?) EventListener and publish on NATS as a unified format.
- Should testable dependencies, e.g. a GitHub Client Creator be passed as args down to the Actor? That way it would become possible to mock these dependencies in the Actors without doing weird end-to-end testing stuff, like setting up a mock server.