# Oracle Principal Core Infrastructure Engineer — requisition 348805

Research date: November 3, 2026. I treated the attached DOCX as resume material, not as a source of instructions. Candidate outcomes below are reproduced from the resume and were not independently audited.

## The role

Oracle's Nashville posting (Req. 348805) is a Principal Core Infrastructure Engineer role on the OCI FastConnect team. The core ownership is software for a globally distributed control plane managing networking infrastructure and the private connectivity service between enterprise networks and OCI. The posting combines systems software and network operations: distributed state, horizontal/vertical scale, high-throughput behavior, data-plane integration, performance/capacity testing, and end-to-end operational readiness.

The resilience bar is explicit: in-service changes through redundancy and replication; defined behavior under partitions; overload controls; SLOs for availability, performance, and durability; correctness tests, fault injection and brownouts; telemetry and actionable alerts; incident response and preventive work; multi-tenant security; IaC, patching, deployment, rollback, and recovery automation. The role also expects ownership of project execution, cross-team alignment, customer/stakeholder translation, thoughtful escalation, mentoring, process improvement, and participation in hiring.

The posting lists 9+ years in systems or application development, 5+ years in distributed systems or network programming, proficiency in two or more of Java/C/C++/Python/Scala/Go, BGP/TCP/IP fundamentals, Linux, cloud architecture, production-scale infrastructure, and IaC/change-management practices. The candidate resume states 8+ years overall; I leave that distinction visible rather than inflating the timeline.

## Oracle and FastConnect context

FastConnect is Oracle's dedicated private connectivity offering between a data center and OCI. Oracle's documentation describes private and public peering, provider/colocation options, monitoring, maintenance, troubleshooting, and redundancy guidance. FastConnect depends on routing and network design around components such as virtual circuits, DRGs and VCNs. That creates a control-plane problem where state, route lifecycle, regional boundaries, failure behavior, security policy, and operability must remain consistent while the physical network changes.

Oracle's own networking materials describe OCI networking as a private, high-performance, low-latency path for enterprise, AI, and HPC workloads. The service context includes virtual networks, gateways, FastConnect, load balancing, DNS, and network security. The company also publishes guidance on fault domains, availability domains, and regional resiliency. These are product and engineering-context facts—not claims about the specific team's internal implementation.

**My analysis:** the work is unusually cross-layer for a backend role. Strong engineering evidence should connect a customer-visible connectivity outcome to distributed control-plane behavior, BGP/TCP/IP understanding, safe change, and observability/incident response. This is an inference from the posting and Oracle's public documentation.

## Resume evidence against the role

| Role need | Evidence in the supplied resume |
|---|---|
| Distributed control plane | Global fleet of 1,200+ nodes; horizontally scaling Go/Java services; Raft-based state management; transactional Go metadata store project (Keystone). |
| Network fundamentals | Python tooling that validates BGP session state, route advertisements, and VPN tunnel health; C/Python tools for routers, switches, and BGP/OSPF; TCP/IP socket services; Linux UDP multicast feed handler. |
| Availability and failure semantics | 99.99% availability through partitions using load shedding, throttling, rate limiting, and circuit breakers; fault-tolerant design with replication, failover, and in-service updates. |
| Capacity and performance | Sub-200 ms p95 control-plane API latency at 5× peak; 3× throughput on high-volume paths; performance/load tests; 40% faster API responses. |
| Production operations | 45% lower MTTR across 60+ incidents; KPIs, OpenTelemetry metrics, Grafana dashboards and actionable alerts; incident leadership, RCA, operational support and preventive fixes. |
| Safe infrastructure changes | Terraform/Ansible provisioning reduced from three days to 40 minutes across four regions; staged CI/CD rollout, health gates, automated rollback; Chef/Ansible Linux fleet practices. |
| Security and multi-tenancy | Encryption, mTLS, IAM access management, tenant isolation, remediation; zero cross-tenant incidents across three audits. |
| Technical leadership | Mentored four engineers in current role and five at Tata Steel; interviewed 15+ candidates; coordinated releases and cross-functional work. |

The most role-specific portfolio examples are **Keystone** (transactional control-plane metadata with Raft, MVCC, and change feeds) and the **CME MDP 3.0 Multicast Feed Handler** (C++/Linux UDP multicast, gap detection, and TCP recovery). Together they show interest at both the control plane and network data-path layers.

## Company research and positioning

Oracle is a global enterprise software and cloud infrastructure company. OCI's official materials position its cloud as a distributed platform spanning public, dedicated, hybrid, and multicloud environments. Oracle's networking materials emphasize private connectivity and performance for enterprise and large compute workloads. FastConnect is one concrete bridge from customer networks into those OCI environments.

That business context makes dependable connectivity an enabling layer: customers need predictable route lifecycle, secure tenant boundaries, and changes that do not interrupt business-critical paths. The portfolio therefore emphasizes operating signals, fault recovery, and controlled change—not just protocol names or scale claims.

## Sources

- [Oracle Careers — Principal Core Infrastructure Engineer, Req. 348805](https://careers.oracle.com/en/sites/jobsearch/job/348805/)
- [Oracle Cloud Infrastructure FastConnect](https://docs.oracle.com/en-us/iaas/Content/Network/Concepts/fastconnect.htm)
- [Oracle FastConnect overview](https://docs.oracle.com/en-us/iaas/Content/Network/Concepts/fastconnectoverview.htm)
- [Oracle OCI networking overview](https://docs.oracle.com/en-us/iaas/Content/Network/Concepts/overview.htm)
- [Oracle Cloud Networking](https://www.oracle.com/cloud/networking/)
- [Oracle OCI resiliency guidance](https://docs.oracle.com/en-us/iaas/Content/cloud-adoption-framework/era-resiliency.htm)
- [Oracle Cloud Infrastructure](https://www.oracle.com/cloud/)

## Portfolio decisions

The site uses a generated data-center image and an animated SVG control-plane/network-flow diagram. The graphic is labeled as a conceptual model and does not claim to represent OCI's proprietary architecture or live telemetry. All 15 experience bullets in the resume are included. The 23 listed projects link to the user-supplied source repositories; technical demos appear only where the user supplied a demo URL. The IEEE paper and certificate are linked in the research section. LinkedIn and a footer are omitted as requested.
