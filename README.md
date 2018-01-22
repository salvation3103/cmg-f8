# Openshift on AWS
A step-by-step instructions to set up Openshift Origin cluster upon AWS EC2 instances.

# Introduction
Openshift is a Platform as a Service (PaaS) that relies on Docker and Kubernetes Docker Management. When deploying Openshift Origin on AWS, there will be some specific settings to be done for the cluster to be able to access EC2 instances, create/delete persistent volumes, create ELB,...

An Openshift cluster must consist at least:
- 1 master
- 1 etcd
- 1 node

This guide will help you to set up a production ready environment with:
- one master, including etcd
- 2 nodes

For more Openshift cluster models, and definition, go here: https://docs.openshift.org/latest/install_config/install/planning.html#environment-scenarios

# Prerequisites
Check prerequites for Openshift Origin requirements: https://docs.openshift.org/latest/install_config/install/prerequisites.html#install-config-install-prerequisites

## EC2 instances:
- Master: 
 * 4CPUs, 16G (m4.xlarge)
 * 80G / + /var
 * 10G /home
 * 20G free unallocated storage (for setting up docker storage later)
- Node1+Node2:
 * 2 CPU, 16GB (m4.xlarge)
 * 60G / + /var
 * 10G /home
 * 20G free unallocated storage (for setting up docker storage later)
		
