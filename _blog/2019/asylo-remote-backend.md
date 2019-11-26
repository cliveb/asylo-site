---
title: Asylo Enclave Remote Backend
subtitle: Release Announcement
publish_date: 2019-10-31
attribution: Leonid Baraz, Zachary Trudo
order: 17
layout: blog
type: markdown
---
{% include home.html %}

Asylo believes that it is important to have flexibility in how enclave
technology is deployed, while retaining the simple programming model Asylo
provides today. With the release of the Asylo Enclave Remote Backend
(`RemoteBackend`), Asylo continues to meet and improve upon those objectives.

Local enclaves provide execution isolation by means of SGX or another Trusted
Execution Environment. `RemoteBackend` provides execution isolation by placing the
enclave on a separate target server. In addition, `RemoteBackend` doesn't require
any changes in the Enclave itself, so users can layer `RemoteBackend` with other
backend technologies. The target server can have the security properties
required by the user application, whether that be Intel SGX, AMD-SEV, or simply
physical security.

#### Application Model

The `RemoteBackend` utilizes two gRPC peering agents, one on the host machine
running inside the Untrusted application, and the other on the target server
wrapping the Enclave. All Enclave calls and Untrusted calls are still made with
the Asylo API, but are forwarded from one gRPC agent to the other. The
underlying technology, gRPC, allows users to place the user application and
target server across any network routable space. For instance, the user
application could be placed in the cloud, while the target server could be
placed on-prem, or vice versa.

A deeper dive into the technical details can be found here [Asylo Remote Backend
Concepts Document]({{home}}/docs/concepts/remote-backend.html)

#### Conclusion

`RemoteBackend` Enclaves are a big step forward for Asylo, and our team is excited
about this release. It is a large new system and a lot to cover in a short blog
post. Our team looks forward to hearing about how users are using them, so if
you have any questions, comments, or requests please post them to our [Asylo
Users forum](https://groups.google.com/forum/#!forum/asylo-users).
