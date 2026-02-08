---
title: Architecture
description: An overview of the architecture of my home Kubernetes cluster.
---

## Overview

This page provides an overview of the architecture of my home Kubernetes cluster, including the key components and how they interact with each other. The cluster is designed to be scalable, resilient, and easy to maintain, with a focus on using open-source tools and best practices for Kubernetes management. The main tools used in the cluster include Flux for GitOps-based deployment, Cluster Template for managing cluster configuration, and various other tools for monitoring, logging, and security. The architecture is designed to allow for easy expansion and modification as needed, while also ensuring that the cluster remains stable and secure.

## Key Components

### Cluster Template

Cluster Template is used to manage the configuration of the Kubernetes cluster. It allows for defining the desired state of the cluster in a declarative manner, making it easier to maintain and update the cluster over time. This is a simple template from the people over at Home Operations. The templates simplify the iniital setup of the cluster and provide a solid foundation for further customization. Included are key components such as Talos for the operating system, Flux Operator for Git-Ops based deployment and Cilium for networking.

### Flux Operator

Flux Operator is used for GitOps-based deployment of applications and infrastructure changes to the cluster. It continuously monitors the Git repository for changes and automatically applies them to the cluster, ensuring that the cluster is always in sync with the desired state defined in Git. Flux Operator is an advancement of the original Flux tool, providing enhanced features and capabilities for managing Kubernetes clusters in a GitOps manner. There are targets for future development afforded by Flux Operator one of which is resource sets to allow for the grouping and templating of resources to reduce duplication and improve maintainability.

### Talos

Talos is used as the operating system for the cluster nodes. It has been installed bare metal on the cluster node and configured with Cluster Template and Talhelper to automate the configuration. Talos provides a secure and minimal operating system that is optimized for running Kubernetes, with features such as automatic updates, built-in security, and a small attack surface. Configuration is totally done through the use of API calls and minimises the potential for security issues. Talos also provides a minimimal OS optimised for running Kubernetes with minimal other Linux components beyond those required for Kubernetes to run. This minimises the attack surface and reduces the potential for security issues.

Talos ongoing maintenance is managed in a GitOps manner with a combination of Renovate and Tuppr automating OS upgrades. Upgrades are configured to hold by default for manual review as there does tend to be manual steps to modify configuration to accomodate changes in newer versions of Talos. This allows for a balance between automation and control, ensuring that the cluster remains up-to-date while also allowing for manual intervention when necessary.
