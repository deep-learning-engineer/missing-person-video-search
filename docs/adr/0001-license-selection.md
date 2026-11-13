# ADR-0001: License Selection for the Project

-   **Status:** Accepted
-   **Date:** 2026-11-13
-   **Decision Makers:** Eduard Ganzha

## Context

The `missing-person-video-search` project is an open-source ML pipeline
designed to help search-and-rescue teams locate missing persons using
natural-language descriptions.

We want modifications to the project's core source code---particularly
model architectures, training logic, and retrieval algorithms---to
remain available to recipients when distributed. At the same time,
organizations should be able to integrate the project with independent
proprietary systems and keep those components closed-source.

We therefore need a license that permits commercial use and proprietary
integrations while providing limited copyleft protection for the
project's own source files.

## Decision

Use the **Mozilla Public License 2.0 (MPL-2.0)** for the project's
source code.

## Rationale

MPL-2.0 is a weak-copyleft license with a file-level approach:

1.  **Modified covered files:** If a user modifies a file containing
    MPL-covered code and distributes the resulting software, that file
    must remain under MPL-2.0, and its source must be made available
    under the license's terms.
2.  **Independent files:** New files that do not contain MPL-covered
    code may use a different license, including a proprietary license. A
    new file containing copied or incorporated MPL-covered code may
    itself be covered.
3.  **Internal and network use:** MPL-2.0 does not generally require
    disclosure of modifications used only internally or solely on a
    server. Merely providing access to server-side functionality over a
    network does not trigger an AGPL-style source disclosure
    requirement.
4.  **No upstream requirement:** MPL-2.0 does not require users to
    submit changes to this project's repository or publish them to the
    public. Its source-availability obligations apply when covered
    software is distributed.

This provides a balance between sharing modifications to distributed
project files and allowing independent proprietary integrations.

## Alternatives Considered

-   **GNU AGPL-3.0:** Adds a network-use requirement: operators of
    modified AGPL-covered software must offer corresponding source code
    to users interacting with it remotely. This better protects
    network-accessible modifications but may discourage proprietary SaaS
    deployments. It does not automatically make every independent
    component or an organization's entire infrastructure open-source.
-   **GNU GPL-3.0:** Requires source-code availability when covered
    software is distributed, but has no AGPL-style network-use
    requirement. It also offers less flexibility than MPL-2.0 for
    keeping independent files in a larger application proprietary.
-   **MIT / Apache 2.0:** Permissive licenses that allow proprietary
    modifications without requiring their release. They therefore do not
    meet the project's goal of preserving access to modifications of
    covered files when distributed.

## Consequences

**Positive** 
- Commercial use and redistribution are allowed. 
- Distributed modifications to MPL-covered files remain subject to MPL-2.0 and its source-availability requirements. 
- Independent proprietary integration code can remain closed-source. 
- Server-side use alone does not trigger network-based source disclosure.

**Limitations** 
- Private modifications and server-side modifications are not required to be disclosed solely because they exist or are used. 
- Users are not required to contribute changes upstream or publish them publicly. 
- Developers must distinguish independent files from files containing MPL-covered code. 
- Datasets, pretrained weights, and checkpoints are not automatically covered by the source-code license;
their licensing must be considered separately.

------------------------------------------------------------------------

*This ADR documents a project decision and is not legal advice.*

