# Phira Events

Phira has held several events. This page describes how Phira events work within the current project structure.

## Basic Concepts

### Events

An event has a one-to-one correspondence with an event page. Event pages are designed using the UML language; see the [UML documentation](../uml/syntax/README) for details.

Each event has an `owner`, usually set to the organizer’s personal or group account. When an event is hidden, only server admins and its `owner` can see it.

Events have start and end times. Before the start time, the event is visible but not joinable. At the start time, the server sends an in-game message to all players that the event has begun. After the end time, players can no longer register.

Events can be locked. When locked, no one can register, but visibility is unchanged.

After joining, a leaderboard is generated. The ranking rules are configured separately; events are usually kept locked.

### Chart Collections

Chart collections can be created freely and are not tightly tied to events.

An event page can reference one or more chart collections. Charts in those collections are not restricted by fields such as `hidden` and are always visible to all players.

## Running an Event

To run an event, the organizer must provide the following to the current TeamFlos community admin or designated external contact (the “liaison”):

- Event flow or outline
- Event page UML source
- Art assets used in the event page (self-hosting is recommended for server load and availability; the source provided to TeamFlos may include URLs to these assets)
- Chart collection(s) used by the event and the charts they contain

For any additional requirements, confirm with the liaison so feasibility can be assessed in time.
