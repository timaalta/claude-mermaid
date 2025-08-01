# Mermaid Architecture Diagram Syntax Reference

## Overview

Architecture diagrams in Mermaid are used to "show the relationship between services and resources commonly found within the Cloud or CI/CD deployments."

## Basic Syntax

Start an architecture diagram with the keyword `architecture-beta`, followed by components in any order.

## Components

### Groups
Syntax: `group {group id}({icon name})[{title}] (in {parent id})?`

Example:
```
group public_api(cloud)[Public API]
group private_api(cloud)[Private API] in public_api
```

### Services
Syntax: `service {service id}({icon name})[{title}] (in {parent id})?`

Example:
```
service database1(database)[My Database]
service database1(database)[My Database] in private_api
```

### Edges (Connections)
Syntax: `{serviceId}{{group}}?:{T|B|L|R} {<}?--{>}? {T|B|L|R}:{serviceId}{{group}}?`

#### Edge Direction
- Use `L|R|T|B` to specify connection side
- `:` indicates connection point

#### Arrows
- `<` before direction: left arrow
- `>` after direction: right arrow

Example:
```
db:R -- L:server
subnet:R --> L:gateway
```

### Junctions
Syntax: `junction {junction id} (in {parent id})?`

## Icons

Default icons:
- `cloud`
- `database`
- `disk`
- `internet`
- `server`

Can use 200,000+ icons from iconify.design or add custom icons.

## Example Diagram

```
architecture-beta
    group api(cloud)[API]

    service db(database)[Database] in api
    service disk1(disk)[Storage] in api
    service server(server)[Server] in api

    db:L -- R:server
    disk1:T -- B:server
```