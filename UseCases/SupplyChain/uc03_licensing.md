# Use Case 03 - Open source licensing risks

Open source software (OSS) is a critical component 
in the development of modern applications, 
powering everything from infrastructure to end-user features; 
but its use introduces diverse licensing requirements 
that can impose significant legal and operational obligations, 
especially for redistributed software. 
This use case demonstrates how an SBOM can be used 
to effectively manage open source licensing risks 
by serving as a comprehensive inventory 
of all software components within an application, 
along with their respective licenses. 
An enriched SBOM that includes license details, 
full license text, 
and copyright information—elements 
that may be absent from an NTIA-minimum-elements 
compliant SBOM—can provide additional artifacts 
needed for open source license management.

By integrating SBOMs with open source license databases 
and aligning with organizational OSS license policies, organizations 
can proactively identify and mitigate licensing conflicts, 
track compliance obligations,
 and address changes in licensing terms that may introduce legal risks. 
This structured approach empowers legal, development, 
and compliance teams to collaborate effectively, 
ensuring adherence to licensing requirements, 
minimizing legal exposure, and fostering a secure and compliant software supply chain.

Key attributes of this use case are:

* Actors
   - Legal and Compliance Teams, Open Source Program Office (OSPO), Engineering/Development Teams, Procurement Office, Security Teams, Executive/Management Teams
* Business Motivation
   - Protect company from legal risks associated with improperly licensed open source components
* Functional Objectives
   - Empower all actors to collaboratively manage open source software in a legal manner. 
   - Ensure adherence and compliance to the various open source licenses in use, avoiding costly legal penalties or violations. 
   - Provide visibility into the software supply chain to identify licensing conflicts.
* Processes or Steps to Achieve Objectives
   - Determine the specific requirements for the organization's OSS license policy, including acceptable license types, usage restrictions, and compliance obligations.
   - Determine the compatibility of various open source licenses used across different components in the software supply chain. This step helps prevent conflicts that may arise from combining components with incompatible license terms. 
   - Determine the need to update or replace open source components based on changes in licensing terms, discovery of legal risks tied to specific licenses.
   - Identify the license being used for the distribution of a software release version. 
   - Identify the software licenses associated with each component listed in the SBOM by leveraging an open source license database.
   - Identify potential licensing risks, such as restrictive licenses that could impose obligations on proprietary code or licenses requiring source code disclosure.
   - Identify the legal and compliance obligations for any software that incorporates open source components, particularly for products that will be redistributed.
* SBOM Fields Used
   - Component Name
* Added or Cross-linked Data
   - Open source license database such as those maintained by:
      - [SPDX](https://spdx.org/licenses)
      - [OSI](https://opensource.org/licenses)
      - [ecosystem.ms](https://licenses.ecosyste.ms)
* Benefits Achieved
   - Provides specific actions legal teams should take based on the SBOM's license data to protect the organization from potential legal exposure. This includes setting policies for component updates, replacements, or license conflict resolution.
   - Ensures that software vendors and internal teams comply with established OSS license requirements and policies. 

The text of this use case was adapted from [Reference 1](./README.md#references).


