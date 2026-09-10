# Welcome to Humainary

**Systems that interpret themselves**

Humainary is a software research and development lab creating the frontier computational foundations
for situational intelligence in systems of services.

We develop theories, architectures, and working software that enable complex distributed systems to
transform operational evidence into signs, statuses, situations, and projections as they operate.
This gives human and autonomous actors a shared basis for understanding what is happening,
anticipating what may follow, and acting through explicit, bounded possibilities while intervention
remains possible.

Substrates and Serventis are revolutionizing the way we interpret data. By integrating
interpretation into the core of any distributed system, we're transforming operational meaning into
a first-class computational capability. Our groundbreaking research, which draws from semiotics,
cybernetics, holonic flow, and perceptual control theory, is changing the game for how complex,
large-scale software systems see, sense, situate, steer, simulate, and scale.

## How the Pieces Fit

A specification defines a model. A language API projects it. A provider implements the API — the
compatibility kits decide whether it conforms, and Perfkit measures what it costs. Two
specifications layer: Substrates governs circulation, Serventis the vocabularies carried through it.

| Repository                | Role                                                   |
|---------------------------|--------------------------------------------------------|
| [substrates-api-spec]     | The circulation model, language-neutral                |
| [serventis-api-spec]      | The observation model, language-neutral                |
| [specs-api-java]          | Annotations binding Java declarations to a spec clause |
| [substrates-api-java]     | Java projection of the circulation model               |
| [substrates-api-java-tck] | Conformance tests for a Substrates provider            |
| [serventis-api-java]      | Java projection of the observation model               |
| [serventis-api-java-tck]  | Conformance tests for Serventis on a provider          |
| [perfkit-java]            | JMH measurement of a provider's steady-state cost      |

[substrates-api-spec]: https://github.com/humainary-io/substrates-api-spec
[serventis-api-spec]: https://github.com/humainary-io/serventis-api-spec
[specs-api-java]: https://github.com/humainary-io/specs-api-java
[substrates-api-java]: https://github.com/humainary-io/substrates-api-java
[serventis-api-java]: https://github.com/humainary-io/serventis-api-java
[substrates-api-java-tck]: https://github.com/humainary-io/substrates-api-java-tck
[serventis-api-java-tck]: https://github.com/humainary-io/serventis-api-java-tck
[perfkit-java]: https://github.com/humainary-io/perfkit-java

The table is in release order: a specification is published before the projections whose references
resolve against it, and each release is named by an immutable tag the projections pin.

The API repositories publish interface surface only; runtime behavior comes from an SPI provider you
supply. The compatibility kits and Perfkit take that provider's Maven coordinates and build nothing
they measure.

## Public Projects

### [Substrates API Specification][substrates-api-spec]

Language-neutral specification for deterministic signal circulation infrastructure.

The specification defines structural primitives, behavioral contracts, identity semantics, lifecycle
rules, routing behavior, and temporal guarantees for computational networks in which typed values
flow through governed topologies. It is independent of language, runtime, and transport: a
conformant implementation may be an in-process library, a networked service, or a hybrid system.

### [Serventis API Specification][serventis-api-spec]

Language-neutral specification for the observation layer carried over Substrates.

The specification defines what an observation is — a sign, optionally qualified by a dimension —
together with the instruments that emit them, the universal vocabularies every implementation
provides, the rules a new vocabulary must satisfy, and the conformance a suite tests for.
Translation between vocabularies is specified as partial: an implementation may abstain, and
abstention is not an error. The accompanying registry records the registered domain vocabularies,
their membership fixed once published; the rationale document explains the choices without
constraining them.

### [Specification Annotations for Java][specs-api-java]

Traceability annotations binding a Java declaration to the clause that governs it.

`@SpecDoc` names a specification at a pinned tag; `@SpecRef` names the sections a declaration or a
test realizes. Together they make conformance coverage searchable in both directions — from a clause
to what implements and tests it, and from a declaration to what it claims. The annotations are
source-retained and the library has no dependencies, so nothing of it reaches a running system.

### [Substrates Java API][substrates-api-java]

Java projection of the Substrates specification.

This repository publishes the Java API contract for circuits, conduits, pipes, fibers, flows,
windows, cells, tickers, scoped resources, hierarchical identity, and SPI provider discovery. It is
the public interface surface, not the runtime implementation. Runtime behavior is supplied by an SPI
provider while preserving the ordering, lifecycle, and conformance semantics defined by the
specification.

### [Serventis Java API][serventis-api-java]

Semantic signaling framework for service observability and coordination.

Serventis extends Substrates with typed vocabularies for turning operational events into meaningful
signals. Its common model is `Signal = Sign x Dimension`, enabling consistent handling of signs
across services, resources, queues, caches, probes, routers, breakers, actors, agents, transactions,
synchronization primitives, logs, sensors, timers, outcomes, operations, trends, surveys, statuses,
and situations.

Together, these vocabularies support a path from raw emissions to structured conditions, situational
awareness, and coordination traces across distributed software and human-AI systems.

### [Substrates Technology Compatibility Kit][substrates-api-java-tck]

Executable conformance tests for Java providers of the Substrates API.

The kit is the arbiter of what counts as a Substrates provider: emission ordering, causal completion
of cascading work, lifecycle and closure semantics, hierarchical identity, and operator behavior are
exercised against your own implementation. It takes the provider's Maven coordinates and builds
nothing it tests.

### [Serventis Technology Compatibility Kit][serventis-api-java-tck]

Executable conformance tests for the Serventis API on a Substrates provider.

Verifies the semantic layer end to end: sign emission across every vocabulary, the sign sets and
maps that classify them, and the ascent from domain signs into statuses and situations. It runs
against any conformant Substrates provider, confirming that semantic behavior is identical wherever
the signals circulate.

### [Perfkit][perfkit-java]

JMH benchmark suite for Substrates and Serventis providers.

Perfkit measures a provider's steady-state cost: emission and its boundaries, operator chains,
pooled lookup, name and state access, and the semantic ascent layer. Beyond a plain benchmark runner
it offers fixed-setting decision runs, allocation attribution, and batch-size sensitivity checks, so
a reported figure carries the conditions that produced it and can be re-derived on your own
hardware.

## Why Sponsor Us?

Sponsorship supports independent research and engineering at the intersection of semiotics,
cybernetics, observability, and distributed systems infrastructure. It helps move the work from
specification and API contracts toward conformance tooling, runtime providers, benchmarks,
documentation, and production-grade open implementations.

[Sponsor Humainary](https://github.com/sponsors/humainary-io) and help shape the future of
situational intelligence infrastructure.

## License

Copyright (c) 2025-2026 William David Louth.

Each repository states its own license. Current public specification and API repositories are
published under the Apache License, Version 2.0.

## Links

- [Humainary.io](https://humainary.io)
