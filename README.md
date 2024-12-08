# CNCF Linux Foundation Mentorship' 24 With Harbor
This document constitutes my submission for the CNCF Linux Foundation Mentorship' 24 final report. Over the course of this program, I had the privilege of collaborating with Harbor Community and making significant contributions to their Harbor Satellite.

Throughout this period, I embarked on a journey of innovation and collaboration, pushing the boundaries of what the Harbor Satellite could achieve. My work spanned various critical aspects, from enhancing user experience to implementing intricate functionalities. This report outlines the key milestones and accomplishments achieved during this enriching experience.

## Project Overview

Containers have extended beyond their traditional cloud environments, becoming increasingly prevalent in remote and edge computing contexts. These environments often lack reliable internet connectivity, posing significant challenges in managing and running containerized applications due to difficulties in fetching container images. To address this, the project aims to decentralize container registries, making them more accessible to edge devices.

## [Harbor Organization Repository](https://github.com/container-registry/harbor-satellite)
## [Personel Repository](https://github.com/Mehul-Kumar-27/harbor-satellite)

****

### What is Harbor Satellite ?

First let me describe what Harbor is. Harbor is a CNCF open source container registry for managing container images/artifacts securely with policies, role based access control, vulnerability scans and signing. But it has some limitations in the edge locations where Harbor does not perform as expected. In such cases we are developing another solution which could work better in such cases.

Harbor Satellite is a containerized artifact distribution and management solution for edge locations, ensuring consistent, available, and integrity-checked artifacts in edge computing environments at scale.

Containers are running everywhere in the cloud and on small devices. In all those cases, software distribution and management is essential.
- U.S. Air Force Deployed Kubernetes and Istio on an F-16.
- Domino's Pizza is running a K8s Cluster in each of their 10k  branches.
- SNCF is running a Kubernetes Clusters on trains.
- Many Telcos run Kubernetes in each cell tower (RAN) resulting in 100k of registries.

#### The problems Harbor Satellite Solves

- Software Distribution to the Edge
- Management of the software delivery and rollout process
- Manage and distribute software to thousands of sites
- Remotely orchestrate the software distribution process
- Predictable behavior and in poor connectivity situations
- Control image replication and presence
- Optimized resource and bandwidth utilization

![Harbor Satellite](/images/harbor-satellite.svg)
<p align="center"><em>System Overview</em></p>


