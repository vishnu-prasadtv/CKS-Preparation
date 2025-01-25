# CKS-Preparation

## Curriculum

The Certified Kubernetes Security Specialist (CKS) certification is designed to validate an individual's knowledge and skills in securing Kubernetes clusters and applications. Below is a detailed breakdown of the CKS curriculum, including the specific topics and scenarios you should focus on for each domain.

## 1. Cluster Setup (10%)
This domain focuses on securing Kubernetes clusters during their setup and configuration.

Topics to Learn:
- Network Policies: Learn how to define and enforce network policies to restrict traffic between pods.
- Kubernetes API Access:
  - Secure access to the Kubernetes API server.
  - Configure Role-Based Access Control (RBAC) to restrict permissions.
- Securing ETCD:
  - Encrypt data at rest using ETCD encryption.
  - Secure ETCD with TLS certificates.
- Authentication and Authorization:
  - Configure authentication mechanisms (e.g., certificates, tokens).
  - Use RBAC for granular access control.
- Audit Logs:
  - Enable and analyze Kubernetes audit logs.

Scenarios to Practice:
- Setting up RBAC rules to restrict access to specific namespaces.
- Configuring ETCD encryption for sensitive data.
- Creating network policies to restrict traffic between pods.
- Analyzing Kubernetes audit logs for suspicious activity.

## 2. Cluster Hardening (15%)
This domain focuses on hardening the Kubernetes cluster to reduce attack surfaces.

Topics to Learn:
- Minimizing Attack Surface:
  - Disable unused features or APIs.
  - Use namespaces to isolate workloads.
- Pod Security Standards (PSS):
  - Implement Pod Security Admission (PSA) or PodSecurityPolicies (PSP).
- Securing Components:
  - Secure kube-apiserver, kubelet, and other control plane components.
- Restricting Host Access:
  - Avoid privileged containers.
  - Restrict hostPath and hostNetwork usage.
- Securing Metadata:
  - Restrict access to Kubernetes metadata (e.g., Instance Metadata Service).

Scenarios to Practice:
  - Applying Pod Security Standards (e.g., restricted, baseline).
  - Configuring kubelet with secure settings (e.g., read-only port disabled).
  - Preventing privileged containers from running in the cluster.
  - Creating a namespace for workload isolation.

## 3. System Hardening (15%)
This domain focuses on securing the underlying systems and nodes running Kubernetes.

Topics to Learn:
- Operating System Security:
  - Keep the OS and Kubernetes components up to date.
  - Configure firewalls and disable unused ports.
- Kernel Hardening:
  - Use kernel security modules (e.g., AppArmor, SELinux).
  - Limit syscalls using Seccomp profiles.
- Container Runtime Security:
  - Use a secure container runtime.
  - Configure container runtime sandboxing.
- Control Plane Security:
  - Protect the control plane with firewalls and TLS encryption.

Scenarios to Practice:
- Applying Seccomp profiles to restrict syscalls.
- Enforcing AppArmor or SELinux policies on nodes.
- Configuring firewalls to allow only necessary traffic to the cluster.
- Updating Kubernetes components securely.

## 4. Minimize Microservice Vulnerabilities (20%)
This domain focuses on securing applications and workloads running in Kubernetes.

Topics to Learn:
- Image Security:
  - Use trusted base images.
  - Scan container images for vulnerabilities.
- Runtime Security:
  - Monitor running containers for suspicious activity.
  - Enforce resource limits (CPU, memory) to prevent DoS attacks.
- Secrets Management:
  - Use Kubernetes Secrets for sensitive data.
  - Encrypt secrets at rest.
- Application Security:
  - Use securityContext to enforce security policies (e.g., non-root user).
  - Configure liveness and readiness probes securely.

Scenarios to Practice:
- Scanning container images for vulnerabilities using tools like Trivy or Clair.
- Encrypting Kubernetes Secrets using an external key management system (KMS).
- Configuring pods to run as non-root users.
- Setting resource limits to prevent resource exhaustion.

## 5. Supply Chain Security (20%)
This domain focuses on securing the software supply chain.

Topics to Learn:
- Image Signing and Verification:
  - Use tools like Cosign to sign and verify container images.
- Dependency Scanning:
  - Scan application dependencies for vulnerabilities.
- Build Pipeline Security:
  - Secure CI/CD pipelines.
  - Use tools like Tekton or Jenkins with security best practices.
- Registry Security:
  - Secure container registries.
  - Restrict access to private registries.

Scenarios to Practice:
- Signing and verifying container images with Cosign.
- Scanning application dependencies for vulnerabilities.
- Configuring a private container registry with authentication.
- Securing CI/CD pipelines to prevent unauthorized changes.

## 6. Monitoring, Logging, and Runtime Security (20%)
This domain focuses on monitoring and securing running Kubernetes workloads.

Topics to Learn:
-  Monitoring and Logging:
  - Set up monitoring tools like Prometheus and Grafana.
  - Enable Kubernetes audit logs.
- Runtime Threat Detection:
  - Use tools like Falco or Sysdig to detect runtime threats.
- Incident Response:
  - Analyze logs and metrics for suspicious activity.
  - Respond to security incidents (e.g., isolate compromised pods).
-  Forensics:
  -  Collect and analyze data from compromised containers or nodes.

Scenarios to Practice:
- Setting up Falco to detect suspicious activity.
- Configuring Prometheus to monitor cluster metrics.
- Analyzing Kubernetes audit logs for unauthorized access.
- Isolating and investigating a compromised pod.


## General Tips for Preparing
**Hands-On Practice:** Use a lab environment (e.g., Minikube, Kind, or a cloud provider) to practice scenarios.
Simulate real-world attacks and learn how to mitigate them.
**Focus on Security Tools:** Learn tools like Trivy, Falco, Sysdig, Cosign, and Prometheus.

**Understand Kubernetes Concepts:** Be familiar with core Kubernetes objects (e.g., pods, services, deployments).
Understand how Kubernetes networking works.

**Read Kubernetes Documentation:** Refer to the official Kubernetes documentation for security best practices.

**Practice Time Management:** The CKS exam is performance-based with limited time, so practice solving scenarios quickly.

By focusing on these topics and scenarios, you'll be well-prepared for the CKS exam and ready to secure Kubernetes clusters effectively.
