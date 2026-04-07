# Cloud-Native CI/CD Pipeline with Tekton

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Tekton](https://img.shields.io/badge/CI%2FCD-Tekton-blueviolet)](https://tekton.dev/)
[![Kubernetes](https://img.shields.io/badge/Platform-OpenShift%20%2F%20Kubernetes-blue)](https://www.openshift.com/)

This repository contains a fully automated CI/CD pipeline for a Node.js Tax Calculator application, built using **Tekton** and deployed on an **OpenShift/Kubernetes** cluster. 

## 🚀 Project Overview

The goal of this project was to implement an industry-standard "Build, Test, and Deploy" workflow. The pipeline automates the entire lifecycle of the code—from a GitHub commit to a containerized image ready for cloud deployment.

### Key Features:
- **Automated Testing:** Integrated `Jasmine` unit tests to ensure code quality before building.
- **Infrastructure as Code (IaC):** Defined all pipeline logic using Kubernetes-native YAML manifests.
- **Containerization:** Built OCI-compliant images using `Buildah` and pushed them to the IBM Cloud Container Registry.
- **Security:** Implemented Kubernetes Secrets for secure handling of API keys and registry credentials.

## 🛠️ Pipeline Architecture

The pipeline consists of the following automated stages:
1. **Initialize:** Cleans the workspace for a fresh build.
2. **Clone:** Pulls the latest source code from GitHub.
3. **Install:** Handles Node.js dependencies via `npm install`.
4. **Test:** Runs the Jasmine test suite (verified: **7 specs, 0 failures**).
5. **Build & Push:** Uses a Dockerfile to build an NGINX-based image and pushes it to a private container registry.

## 📂 Repository Structure

- `tasks.yaml`: Custom Tekton Task definitions for cleanup, npm install, and testing.
- `pipeline.yaml`: The main orchestration file connecting all tasks into a single workflow.
- `run.yaml`: The execution manifest used to trigger specific PipelineRuns.
- `pvc.yaml`: Defines the Persistent Volume Claim for shared workspace storage.

## 🔧 Skills Demonstrated
- **CI/CD Tools:** Tekton Pipelines, Tekton CLI (`tkn`).
- **Cloud Platforms:** IBM Cloud, Code Engine, OpenShift.
- **DevOps Tools:** Git, Docker/Buildah, Kubernetes `kubectl`.
- **Testing:** Jasmine (Unit Testing for Node.js).

---
*Developed as part of the IBM CI/CD Practice Labs.*