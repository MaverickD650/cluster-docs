# Cluster Docs Built With Zensical

This repository contains the source code for the documentation site for my home Kubernetes cluster, built using [![Zensical](https://zensical.dev/logo.svg)](https://zensical.dev/). The documentation provides an overview of the architecture of the cluster, including key components such as Cluster Template, Flux Operator, and Talos, as well as details on how these components interact with each other to create a scalable, resilient, and easy-to-maintain Kubernetes cluster. The documentation is designed to be comprehensive and user-friendly, with a focus on using open-source tools and best practices for Kubernetes management.

## Building and Running the Documentation Site

Initial build was completed using mise and a python virtual environment to run the zensical CLI. Requirments.txt is provided for the Cloudflare Worker deployment. Renovate is configured to keep dependencies up to date and runs in cluster on a regular schedule. Wrangler.jsonc is provided for the Cloudflare Worker deployment and is configured to use the GitHub integration for seamless deployment on push to main branch.

Everything is a work in progress and I am still learning how to use Zensical and how to best document the cluster, so expect the documentation to evolve over time as I learn more and as the cluster evolves.
