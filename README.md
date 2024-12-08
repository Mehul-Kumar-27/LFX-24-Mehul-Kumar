# CNCF Linux Foundation Mentorship '24: Harbor Satellite

This document serves as my final report for the CNCF Linux Foundation Mentorship '24 program. During this mentorship, I had the privilege of working with the Harbor community and contributing to the development of **Harbor Satellite**, a key project aimed at enhancing containerized artifact distribution for edge environments.

Throughout this program, I engaged in innovation and collaboration, pushing the limits of what Harbor Satellite could achieve. My contributions included improving user experience, implementing advanced functionalities, and addressing critical challenges. This report highlights the key milestones and accomplishments during this enriching journey.


## Project Overview

As containers continue to gain traction beyond traditional cloud environments, they are increasingly being deployed in remote and edge computing scenarios. However, these environments often suffer from unreliable internet connectivity, creating challenges in managing and running containerized applications due to difficulties in fetching container images.

The goal of this project is to decentralize container registries, making them more accessible and functional for edge devices, even in connectivity-constrained environments.

- **[Harbor Organization Repository](https://github.com/container-registry/harbor-satellite)**
- **[Personal Repository](https://github.com/Mehul-Kumar-27/harbor-satellite)**


****

## What is Harbor Satellite?

To understand Harbor Satellite, it's essential first to understand **Harbor**. Harbor is a CNCF open-source container registry designed to manage container images and artifacts securely. It includes features like policies, role-based access control (RBAC), vulnerability scanning, and image signing. However, Harbor has limitations in edge locations where it does not perform as reliably due to connectivity, scalability and hardware challenges.

**Harbor Satellite** addresses these gaps by providing a containerized artifact distribution and management solution specifically tailored for edge environments. It ensures consistent, available, and integrity-verified artifacts, even at scale.

### The Growing Need for Edge Computing Solutions

Containers are now running everywhere, from the cloud to edge devices. Effective software distribution and management are essential in these scenarios. Examples include:
- The U.S. Air Force deploying Kubernetes and Istio on F-16 fighter jets.
- Domino's Pizza running Kubernetes clusters in 10,000+ branches globally.
- SNCF (French National Railways) operating Kubernetes clusters on trains.
- Telecommunications providers managing Kubernetes in thousands of cell towers, resulting in over 100,000 registries.

### Challenges Solved by Harbor Satellite

Harbor Satellite addresses several key issues:
1. **Software Distribution to the Edge**: Ensures seamless delivery of software to remote and edge locations.
2. **Management of Software Delivery and Rollout**: Orchestrates software updates and distribution remotely.
3. **Scalability**: Supports software distribution across thousands of sites efficiently.
4. **Resilience in Poor Connectivity**: Maintains predictable behavior and performance in environments with unreliable internet.
5. **Controlled Image Replication**: Provides fine-grained control over image replication and presence across devices.
6. **Optimized Resource Usage**: Minimizes bandwidth and resource utilization to suit edge environments.

***

![Harbor Satellite](/images/harbor-satellite.svg)
<p align="center"><em>System Overview</em></p>

***

### Brief Overview of Components

Harbor Satellite consists of two main components: **Ground Control** (located in the cloud or a location with reliable connectivity) and **Satellite** (deployed at the edge location). Additionally, there is a central repository that hosts container images and OCI artifacts, which are replicated by Harbor Satellite.

- #### Ground Control
  Ground Control is responsible for monitoring Satellites deployed at edge locations. It authenticates Satellites and provides the capability to specify which images or artifacts should be replicated. Ground Control manages permissions for Satellites, creates credentials for them, and securely provides these credentials.

  It is a stateful component, utilizing a PostgreSQL database to store data about the various Satellites.

- #### Satellite
  The Satellite component operates at remote edge locations. It replicates images from the central repository and includes an **OCI Zot repository**, which runs alongside it to store images locally at the edge. Alternatively, users can provide their own repository if they prefer not to use the built-in Zot repository.

