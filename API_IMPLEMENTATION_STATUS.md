# API Implementation Status

Documents the capability exposed by JavaScript durable functions and the status of implementation within Python

| Class Exposed On	| Method	| In Python?	| Documentation |
| :---------------- | :-------- | :------------ | :------------ |
| Orchestrator | CallActivity | yes | Schedules an activity function named `name` for execution.
| Orchestrator | CallActivityWithRetry	| yes | Schedules an activity function named `name` for execution with retry options.
| Orchestrator | all | yes | Similar to Promise.all. When called with `yield` or `return`, returns an array containing the results of all [[Task]]s passed to it. It returns when all of the [[Task]] instances have completed.
| Orchestrator | any | yes | Similar to Promise.race. When called with `yield` or `return`, returns the first [[Task]] instance to complete.
| Orchestrator | waitForExternalEvent	| yes | Waits asynchronously for an event to be raised with the name `name` and returns the event data.
| Orchestrator | continueAsNew	| yes | Restarts the orchestration by clearing its history.
| Orchestrator | callEntity | TBD | Calls an operation on an entity, passing an argument, and waits for it to complete.
| Orchestrator | callSubOrchestrator| TBD |Schedules an orchestration function named `name` for execution.
| Orchestrator | callSubOrchestratorWithRetry |	TBD | Schedules an orchestrator function named `name` for execution with retry options.
| Orchestrator | callHttp | yes | Schedules a durable HTTP call to the specified endpoint.
| Orchestrator | createTimer | yes | Creates a durable timer that expires at a specified time.
| Orchestrator | getInput | no | Gets the input of the current orchestrator function as a deserialized value.
| Orchestrator | setCustomStatus | no | Sets the JSON-serializable status of the current orchestrator function.
| Orchestrator | currentUtcDateTime | yes | Gets the current date/time in a way that is safe for use by orchestrator functions.
| Orchestrator | newUuid | yes | Creates a new GUID that is safe for replay within an orchestration or operation.
| client | createCheckStatusResponse | yes| Creates an HTTP response that is useful for checking the status of the specified instance.
| client | createHttpManagementPayload | no | Creates an [[HttpManagementPayload]] object that contains instance management HTTP endpoints.
| client | getStatus | yes | Gets the status of the specified orchestration instance.
| client | getStatusAll | yes | Gets the status of all orchestration instances. 
| client | getStatusBy | yes | Gets the status of all orchestration instances that match the specified conditions.
| client | purgeInstanceHistory | yes | Purge the history for a concrete instance.
| client | purgeInstanceHistoryBy | yes | Purge the orchestration history for instances that match the conditions.
| client | raiseEvent | yes | Sends an event notification message to a waiting orchestration instance.
| client | readEntityState | TBD | Tries to read the current state of an entity. Returns undefined if the entity does not exist, or if the JSON-serialized state of the entity is larger than 16KB.
| client | rewind | TBD | Rewinds the specified failed orchestration instance with a reason.
| client | signalEntity | TBD | Signals an entity to perform an operation.
| client | startNew | yes | Starts a new instance of the specified orchestrator function.
| client | terminate | yes | Terminates a running orchestration instance.
| client | waitForCompletionOrCreateCheckStatusResponse | yes | Creates an HTTP response which either contains a payload of management URLs for a non-completed instance or contains the payload containing the output of the completed orchestration. 