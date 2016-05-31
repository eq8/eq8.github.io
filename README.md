# Overview

EQuateJS loosely implements CQRS/ES - or the more modern Flux - architecture for building backend web APIs. Here's how it works.

## Core Building Blocks
The core building blocks are:

- commands in the form of **events** that update the application state
- **queries** return the current state of the application

The core API provides an ability to register handlers for events and queries but - more importantly - it also allows adding new registrars.

- **registrars** are layers of abstractions that map to sets of events or queries

## Default Registrars

While events and queries by itself are already powerful, sometimes you'll run into issues   of polluting your events from unintentionally providing it with more context.

For example, in *express*, your typical `req` object usually gets populated with additional context like `req.user` as it goes down the middleware chain.

With *actions* and *views*, the request message is separated from the technical contexts and handlers are provided via the `register` API to map those into events and queries.

- **actions** are higher level abstractions that allow mapping of user intentions and contexts to events
- **views** applies the same context mapping for queries

## References

For a comprehensive introduction to CQRS/ES and Flux, check out the following links:

- [CQRS](http://martinfowler.com/bliki/CQRS.html)
- [Event Sourcing](http://martinfowler.com/eaaDev/EventSourcing.html)
- [Reference 3: Introducing Event Sourcing](https://msdn.microsoft.com/en-us/library/jj591559.aspx#sec4)
- [Flux Architecture](https://facebook.github.io/flux/docs/overview.html)
