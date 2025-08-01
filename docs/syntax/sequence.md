# Mermaid Sequence Diagram Syntax Reference

## Overview

A sequence diagram is an interaction diagram that shows how processes operate with one another and in what order.

## Basic Syntax

### Participants

Participants can be defined implicitly or explicitly:

```mermaid
sequenceDiagram
    participant Alice
    participant Bob
    Bob-->Alice: Hi Alice
    Alice-->Bob: Hi Bob
```

### Actors

Use the `actor` keyword to use an actor symbol instead of a rectangle:

```mermaid
sequenceDiagram
    actor Alice
    actor Bob
    Alice->Bob: Hello
```

### Aliases

Create convenient identifiers with descriptive labels:

```mermaid
sequenceDiagram
    participant A as Alice
    participant J as John
    A->J: Hello John
```

## Message Types

Ten arrow types are supported:

| Type | Description |
|------|-------------|
| `->` | Solid line without arrow |
| `-->` | Dotted line without arrow |
| `->>`| Solid line with arrowhead |
| `-->>`| Dotted line with arrowhead |
| `<<->>`| Bidirectional solid line (v11.0.0+) |
| `<<-->>`| Bidirectional dotted line (v11.0.0+) |
| `-x` | Solid line with cross |
| `--x` | Dotted line with cross |
| `-)` | Solid async line |
| `--)`| Dotted async line |

## Advanced Features

### Activations

Activate/deactivate actors:

```mermaid
sequenceDiagram
    Alice->>+John: Hello
    John-->>-Alice: Response
```

### Notes

Add notes to the diagram:

```mermaid
sequenceDiagram
    Note right of John: Explanation text
    Note over Alice,John: Interaction note
```

### Loops

Create loop structures:

```mermaid
sequenceDiagram
    loop Every minute
        John-->John: Check health
    end
```

### Alternatives

Handle conditional paths:

```mermaid
sequenceDiagram
    alt Condition A
        Alice->>Bob: Do A
    else Condition B
        Alice->>Bob: Do B
    end
```