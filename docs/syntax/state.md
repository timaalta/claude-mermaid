# Mermaid State Diagram Syntax Reference

## Overview

State diagrams describe system behavior through states and transitions between them. A state diagram represents how a system moves between different states based on events or conditions.

## Basic Syntax

### States

States can be defined in multiple ways:

1. Simple state with an ID:
```mermaid
stateDiagram-v2
    stateId
```

2. State with description:
```mermaid
stateDiagram-v2
    state "State description" as s2
```

3. State with ID and description:
```mermaid
stateDiagram-v2
    s2: This is a state description
```

### Transitions

Transitions are represented using the `-->` arrow:

```mermaid
stateDiagram-v2
    s1 --> s2
    s1 --> s2: Transition description
```

### Start and End States

Special `[*]` syntax indicates start and end states:

```mermaid
stateDiagram-v2
    [*] --> s1
    s1 --> [*]
```

## Advanced Features

### Composite States

Nested states can be created using `state` keyword and `{}`:

```mermaid
stateDiagram-v2
    state First {
        [*] --> second
        second --> [*]
    }
```

### Choice and Forks

Represent decision points and parallel paths:

```mermaid
stateDiagram-v2
    state if_state <<choice>>
    [*] --> IsPositive
    IsPositive --> if_state
    if_state --> False: if n < 0
    if_state --> True: if n >= 0

    state fork_state <<fork>>
    [*] --> fork_state
    fork_state --> State2
    fork_state --> State3
```

### Notes

Add descriptive notes to states:

```mermaid
stateDiagram-v2
    State1: The state with a note
    note right of State1
        Important information!
    end note
```

### Concurrency

Use `--` to represent concurrent states:

```mermaid
stateDiagram-v2
    [*] --> Active
    state Active {
        [*] --> NumLockOff
        NumLockOff --> NumLockOn : EvNumLockPressed
        NumLockOn --> NumLockOff : EvNumLockPressed
        --
        [*] --> CapsLockOff
        CapsLockOff --> CapsLockOn : EvCapsLockPressed
        CapsLockOn --> CapsLockOff : EvCapsLockPressed
    }
```

## Example: Order Processing State Diagram

```mermaid
stateDiagram-v2
    [*] --> Pending
    Pending --> Processing : Start Processing
    Processing --> Shipped : Complete Order
    Processing --> Cancelled : Cancel Order
    Shipped --> Delivered : Package Delivered
    Cancelled --> [*]
    Delivered --> [*]
```