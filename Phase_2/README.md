# Kubernetes Deployment Guide

## Table of Contents
- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Cluster Setup](#cluster-setup)
- [Deployment](#deployment)
- [Configuration Management](#configuration-management)
- [Autoscaling](#autoscaling)
- [Monitoring](#monitoring)
- [CronJobs](#cronjobs)
- [Files Included](#files-included)

## Overview
This guide provides step-by-step instructions for setting up a Kubernetes cluster, deploying a web application, and configuring essential Kubernetes features such as scaling, monitoring, and automation.

## Prerequisites
- Docker installed
- Kubernetes CLI (`kubectl`) installed
- Docker Desktop installed with Kubernetes enabled

## Cluster Setup
1. Ensure Kubernetes is enabled in Docker Desktop:
   - Open Docker Desktop
   - Go to **Settings > Kubernetes**
   - Check **Enable Kubernetes** and apply the changes
   - Wait for Kubernetes to start

2. Verify the cluster is running:
   ```sh
   kubectl get nodes
   ```

## Deployment
1. Apply the deployment manifest:
   ```sh
   kubectl apply -f gilz-deployment.yaml
   ```
2. Apply the service to expose the application:
   ```sh
   kubectl apply -f gilz-service.yaml
   ```

## Configuration Management
- Apply the ConfigMap:
  ```sh
  kubectl apply -f gilz-config.yaml
  ```
- Apply the Secret:
  ```sh
  kubectl apply -f gilz-docker-secret.yaml
  ```

## Autoscaling
1. Install the metrics server (required for HPA):
   ```sh
   kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
   ```
2. Apply the Horizontal Pod Autoscaler (HPA):
   ```sh
   kubectl apply -f gilz-hpa.yaml
   ```

## Monitoring
To monitor pod metrics:
```sh
kubectl top pods
```
To check the status of the HPA:
```sh
kubectl get hpa
```

## CronJobs
1. Apply the CronJob manifest:
   ```sh
   kubectl apply -f gilz-cronjob.yaml
   ```
2. Verify the CronJob:
   ```sh
   kubectl get cronjobs
   ```

## Files Included
- `gilz-config.yaml` - ConfigMap for environment variables
- `gilz-cronjob.yaml` - CronJob definition for periodic tasks
- `gilz-deployment.yaml` - Deployment manifest
- `gilz-docker-secret.yaml` - Secret for private Docker registry access
- `gilz-hpa.yaml` - Horizontal Pod Autoscaler configuration
- `gilz-service.yaml` - Service definition for exposing the application

## Conclusion
This setup provides a robust Kubernetes deployment with scaling, monitoring, and automation features. Modify the manifests as needed to fit your requirements!

