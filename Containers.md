# Containers: What Problem Do They Actually Solve?

A lot of the benefits commonly attributed to containers are not unique to containers.

Linux already provides:

- cgroups (CPU, memory, I/O limits)
    
- namespaces (process and network isolation)
    
- capabilities and seccomp (security controls)
    
- systemd (service management, restarts, logging)
    
- writable filesystems and volumes
    

Schedulers such as Nomad can use these features directly without containers.

## What containers are really good at

Containers provide a standard artefact format that bundles:

- application code
    
- filesystem contents
    
- runtime metadata
    
- resource requirements
    
- execution instructions
    

This allows infrastructure to treat workloads uniformly regardless of whether they are written in Go, Python, Java, Node, or something else.

The deepest advantage is **runtime-neutral packaging**.

Instead of:

- Go binary
    
- Python virtualenv
    
- Java JAR
    
- Node application
    

everything becomes:

- OCI image
    

This greatly simplifies tooling, deployment, and operations.

## What could be done without containers

The following do not fundamentally require containers:

- Resource limits
    
- Sidecars
    
- Service meshes
    
- Health checks
    
- Rolling deployments
    
- Secrets management
    
- Process supervision
    
- Logging
    

These are Linux, systemd, or scheduler capabilities.

## What becomes harder without containers

These are possible without containers, but require more custom tooling:

- Security scanning
    
- Software bill of materials (SBOMs)
    
- Signing
    
- Provenance tracking
    
- Artefact registries
    

OCI provides standard formats and conventions that make these tools easier to build.

## What containers genuinely do well

### Runtime-neutral packaging

Infrastructure does not need to care what language is being used.

### Layered distribution

OCI images are built from layers.

For example:

- Base OS layer
    
- Runtime layer
    
- Company dependencies layer
    
- Application layer
    

When only the application changes, only the changed layer must be transferred.

This enables efficient caching and deduplication across machines and services.

## When containers matter less

For a small Go-focused organisation with:

- static binaries
    
- systemd
    
- a few services
    
- a small number of servers
    

containers provide relatively little technical benefit.

## Why containers won

Containers did not win because they introduced resource limits, service management, or isolation.

They won because they became the industry's standard format for packaging, distributing, scanning, signing, caching, and scheduling workloads.