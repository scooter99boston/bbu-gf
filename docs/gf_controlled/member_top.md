# Member Technical and Organizational Policies

This is a Controlled Document of the Bedrock Governance Framework was approved by the Bedrock Consortium Board of Directors.

| Document Name | Member Technical and Organizational Policies |
| --- | --- |
| Version | v0.9 |
| Approval Date | |
| Status | Pre-Launch Phase: Governance Framework Development |
| Governs | General Security Policies, Node Technical Policies, General Security Policies, Node Security Policies, Operating Policies, Node Selection Algorithm, Permissioned Test Network Policies, Reporting Policies |
| Governed By | Bedrock Governance Framework Work Group, [Sovrin Technical Steering Committee](https://sovrin.org/wp-content/uploads/Sovrin-Technical-Governance-Board-Charter-V4.pdf) |

## 1. Ledger Software Policies

1. The Bedrock Board of Directors MUST decide the software technology and version used by all Nodes (Validator, Observer). This software is referred to as the *Bedrock Open Source Code*.
2. The Bedrock Board of Directors MUST require the TSC to establish best practices for continuous delivery and integration of the *Bedrock Open Source Code* using containerization.
3. The Bedrock Board of Directors MUST require the TSC and/or the Utility Service Provider to deploy an upgrade notification process that will allow Stewards to automatically recognized and act when upgrades are available.   
4. The Bedrock Board of Directors MAY leverage the Technical Steering Committee (TSC) or another 3rd party service to maintain a version of the Bedrock Open Source Code.
5. The Bedrock Board of Directors SHOULD require the TSC and/or the Utility Service Provider to automate any prescribed tools that are expected to be used by a node.
6. The Bedrock Board of Directors MUST require the TSC and/or the Utility Service Provider to clearly articulate the mechanism by which a Steward schedules and communicates downtime.

## 2. General Security Policies

1. A Member MUST maintain and follow IT security policies and practices that are integral to maintaining protection of all services provided in association with the Participation Agreement (“Member Services”). These policies MUST be mandatory for all employees of the Member involved with providing the Member Services. The Member shall designate its CIO or another officer to provide executive oversight for such policies, including formal governance and revision management, employee education, and compliance enforcement.
2. A Member MUST review its IT security policies at least annually and amend such policies as the Member deems reasonable to maintain protection of its Member Services.
3. Because Node administrators are a potential threat vector, a Member MUST maintain and follow its standard mandatory employment verification requirements for all new hires involved with providing its Member Services and will extend such requirements to wholly-owned subsidiaries involved with providing its Member Services. In accordance with the Member's internal process and procedures, these requirements MUST be periodically reviewed and include, but may not be limited to, criminal background checks, proof of identity validation, and additional checks as deemed necessary by the Member. Each Member company is responsible for implementing these requirements in its hiring process as applicable and permitted under local law.
4. Employees of a Member involved with providing its Member Services MUST complete security and privacy education annually and certify each year that they will comply with the Member's ethical business conduct, confidentiality, security, privacy, and data protection policies. Additional policy and process training MUST be provided to persons granted administrative access to components that are specific to their role within the Member's operation and support of its Member Services.
5. If a Member hosts its Node in its own data center, the Member's security policies MUST also adequately address physical security and entry control according to industry best practices.
6. If the Member hosts its Node using a third-party Hosting Provider, the Member MUST ensure that the security, privacy, and data protection policies of the Hosting Provider meet the requirements in this document.
7. A Member MUST make available to the Bedrock Consortium upon request evidence of stated compliance with these policies and any relevant accreditations held by the Member, including certificates, attestations, or reports resulting from accredited third-party audits, such as ISO 27001, SSAE SOC 2, or other industry standards.


## 3. General Node Policies
A Member Node:

1. MUST be available to run as a Validator Node or Observer Node on any of the formal ledgers associated with the Utility environments (i.e.: prod, stage, dev)
1. MUST run a release of the Bedrock Open Source Code that has been approved and designated by the Bedrock Board of Directors and Technical Steering Committee (TSC).
1. MUST facilitate an upgrade to a new version of the Bedrock Open Source Code within three (3) business days of a new release that has been:

	1. recommended by the TSC, and
	2. accepted by the Bedrock Consortium.

1. MUST register all Node configuration data in a timely manner and keep information up to date within three (3) business days of changes.
1. MUST have at least two (2) IT-qualified persons assigned to administer the node, and at least one other person that has adequate access and training to administer the Node in an emergency, such as the network being unable to reach consensus or being under attack. See the TSC regarding specific *Crisis Management Plan* details. See [Issue 23](https://github.com/bedrock-consortium/bbu-gf/issues/23).
1. MUST supply contact info for all administrators to the Bedrock Consortium, whose accuracy is tested at least quarterly (e.g., by acknowledging the receipt of an email or text within 24hrs).
1. MUST recover the system from failure in one hour or less.


## 4. Node Technical Policies
For all ledgers within the Utility environments list, the following requirements apply to Nodes on the ```prod``` instance of the Utility. These requirements may be downgraded from MUST to SHOULD for any Nodes on ledgers that are for non-production purposes.

1. MUST run on robust server-class hardware.
2. If a Node is run on a VM, the Member:

	1.  MUST run on a mainstream hypervisor that receives timely patches from its vendor or community.
	2. SHOULD apply hypervisor patches on a regular basis.

3. The Node MUST run in an OS that is dedicated to the validator, i.e., a single-purpose (physical or virtual) machine that MUST run Bedrock Open Source Code, MAY run other software approved by the TSC, and MUST NOT run any other software. Software required to support the node, such as monitoring, backup, and configuration management software, are approved as a general category. However, Members should discuss with the TSC any software packages that transmit between the Member Node and the outside.
4. MUST run a server with compatible versions of the operating systems supported by the Hyperledger Indy Node requirements as documented in the release notes.
5. MUST have adequate compute power (in late 2020, 8 or more cores is considered adequate).
6. MUST have adequate RAM (in late 2020, 32 GB of RAM is considered adequate).
7. MUST have at least 1 TB, with the ability to grow to 2 TB, of reliable (e.g., RAIDed) disk space, with an adequately sized boot partition.
8. MUST have a high-speed connection to the internet with highly available, redundant pipes (as of late 2020, 100 Mbps was considered adequate).
9. MUST have the following dedicated NICs:

	1. a public NIC for all Validator-to-Validator consensus traffic that is a stable, static, world-routable IP address.
	2. a private NIC for all CLI-to-Validator traffic

10. MUST prevent traffic originating from the Validator node to reach the Validator's intranet domain.  
11. MUST be implemented in a way that does not endanger Bedrock's high availability architecture, which is pool-based rather than node-based. Nodes should not take more responsibility for high availability than what is contemplated by the Node Selection Algorithm. For example, they should listen at exactly one pair of network addresses (see 3.9 above), using exactly one set of keys to respond to BBU/Indy protocol traffic at any one time, and adhere to a minimal failover recovery delay period specified by the Bedrock Consortium (or 30 seconds if not specified).
12. MUST have a system clock that is demonstrably in sync with well-known NTP servers.
13. SHOULD have a power supply consistent with high availability systems.


## 5. Node Security Policies
A Member:

1. MUST maintain its [CLI Private Key](../gf_info/glossary.md) on a separate machine from the machine that runs their node. This machine, called the “CLI (Command Line Interface) system”, uses the *CLI Private Key* to authorize the Node to participate in the pool, and is thus the basis for trust for the node and the Member's identity on the network. The CLI system is not required to have high-end hardware, but in terms of IT best practices for security, it must meet or exceed the standards for the Node (see following items).
2. MUST provide certification that their Node runs in a locked datacenter with appropriate levels of security, including the specifications that they target (e.g., SSAE 16 type II compliance; other standards may also be acceptable).
3. MUST assert that their Node is isolated from internal systems of a Member (because the Validator Node is publicly visible and thus an inappropriate candidate for access to privileged internal networks).
4. MUST assert that their Node, and its underlying systems, uses state-of-the-art authentication for remote access via   SSH with key plus password plus source IP firewall rule.
5. SHOULD implement two-factor authentication for SSH access.
6. MUST NOT allow access (remote or local) to the Node or CLI systems by anyone other than assigned admins.
7. MUST apply the latest security patches within one (1) week or less (24 hours or less is recommended).
8. MUST attest that the Node runs on a server protected by a firewall that, at minimum:

	1. Disallows public ingress except on ports used by the Node software (different machines may choose to expose ledger features on different ports, so no standard port setup is required).
	1. Optionally enables SSH, Remote Desktop, and similar remote access tools but constrains ingress for these tools in some way that excludes the public but allows access for admins.
	1. Locks down egress ports to limit the ability to jump from Node to some other location.

9. MUST run a set of TSC prescribed tools and receive TSC approval of the results before the Node is authorized to participate in consensus.
10. MUST run a set of TSC prescribed tools from time to time as requested by the TSC and provide the test results report to the TSC within three (3) business days.

See [Issue 24](https://github.com/bedrock-consortium/bbu-gf/issues/24).

## 6. Node Operating Policies
A Member:

1. MUST equip at least two (2) technical points of contact responsible for administering the Member Node with an SMS-capable device for alerting.
2. SHOULD aim to achieve at least 99.9% (three nines) uptime for their Node (this amounts to about 1.4 minutes of downtime per day or 9 hours per year).
3. SHOULD coordinate downtime with other Members in advance via a mechanism as determined from time to time by agreement between the TSC and any other relevant Bedrock Consortium Governing Body.

## 7. Node Selection Algorithm
1. The TSC will take direction from the Bedrock Consortium Board of Directors, or a designated Bedrock Workgroup, regarding the configuration parameters associated with the deployment of the Node Selection Algorithm.
1. The selection of active Validator Nodes at any point in time, at least on the BBU, MUST be governed by the Node Selection Algorithm.
2. Non-technical inputs or policy decisions implemented by the Node Selection Algorithm MUST be approved by the Bedrock Consortium Board of Directors.
3. At any point in time, the Node Selection Algorithm MUST represent the TSC’s best efforts at designing an algorithm that applies the Core Principles of the Bedrock Consortium Governance Framework. Recognizing the inherent tension and tradeoffs between some of the Core Principles, the design of this algorithm should give priority to balancing:

	1. The Decentralization by Design principles, in particular the principles of Diffuse Trust and High Availability. See *Diversity Goals* below.
	1. The Security by Design principles, in particular the principles of System Diversity and Secure Failure. See *Diversity Goals* below.

4. A human-readable, understandable, and explainable description of the current design of the algorithm as approved by the TSC MUST be published by the TSC in the official Sovrin Foundation Code Repository and made visible to all Members via a web page on the Bedrock Consortium website.

## 8. Reporting Policies
1. A Member MUST report to the responsible Bedrock Consortium Governing Body any substantive change to the configuration or location of a Node within five (5) business days of the change.

## 9. Diversity Goals
While the *Node Selection Algorithm* will be *tuned* from time-to-time to address Performance as well as Decentralization Security by Design principles, the following diversity guidelines SHOULD be considered:

| Concern | Policy |
| --- | --- |
| Should restrictions be applied that limit the number of  nodes in the active Validator Pool that are hosted in a specific data center?| See IaaS Policy |
| Should restrictions be applied that limit the number of  nodes in the active Validator Pool that are hosted in a specific geolocation? | See IaaS Policy |
| Should restrictions be applied that limit the number of  nodes in the active Validator Pool that can be hosted on the same IaaS? | **YES** - See IaaS Policy |
| Should restrictions be applied that limit the number of  nodes in the active Validator Pool that can be hosted by the same hosting provider? | **NO** - See Hosting Provider Policy |

### IaaS Policy
1. If a Steward desires to take on the compliance costs for in-house hosting certification, this will add diversity to the Utility.
2. Some Stewards MAY desire to meet the needs of their membership obligations using external cloud providers that offer the necessary security and compliance certifications and offers world-wide data center coverage. The following SHOULD be considered when Stewards leverage any form of outsourced cloud computing (*Infrastructure as a service (IaaS)*, *Software as a service (SaaS)*, or *Platform as a service (PaaS)*):

	1. In 2019, [Gartner listed](https://www.cbronline.com/news/cloud-iaas-gartner) the following top 6 global enterprise cloud providers: AWS, Microsoft, Alibaba, Google, Oracle  and IBM. These providers have the ability to meet two key requirements for Stewards:

		1. Standards compliance and certification;
		2. Many (>15) availability zones across numerous (>5) geographic regions.

	2. There is no simple way to determine the appropriate degree of granularity relative to geolocation restrictions. Instead, limits SHOULD be applied to the number of nodes across availability zones within a particular IaaS.

		1. No more that 10% of total Active Validator Pool SHOULD be hosted in the same availability zones of an IaaS.
		2. Assuming an Active Validator Pool of 25, this would be no more than 2 nodes on any given availability zone for an IaaS.

	3. To minimize the impact IaaS vulnerabilities may have on  consensus, no more than 33% of the Active Validator Pool should be running on a specific IaaS.
	4. Assuming an Active Validator Pool of 25, this would imply that no more than 8 nodes should be hosted on any one IaaS.

### Hosting Provider Policy
The relationship between a Steward and a Hosting Provider is outside the scope of the BBU-GF. Hosting provider decisions have financial impacts on Stewards and as a result the Consortium SHOULD NOT insert itself into that decision making process.

While no restrictions are suggested, a Steward SHOULD expect hosting providers to offer multi-cloud hosting options for  Indy-Node SaaS services so that IaaS policies can be observed across the BBU.
