# Curriculum

Starting from October 10, 2024, the Certified Kubernetes Security Specialist (CKS) exam will undergo several significant updates to ensure that certified professionals possess the most current skills to secure Kubernetes environments. The changes, aimed at keeping pace with evolving security practices, are reflected across all domains of the exam. These updates are critical for candidates looking to ensure they are equipped to handle the security challenges in modern Kubernetes environments.

![image](https://github.com/user-attachments/assets/62c62c51-15a0-4dc8-a6b0-70cb09533684)


![image](https://github.com/user-attachments/assets/7edf95bb-82ab-4f7d-a859-9589f13cfa52)

## Cluster Setup Domain Updates (Weightage Increased from 10% to 15%)

The Cluster Setup domain sees a notable increase in its weight from 10% to 15%, indicating its growing importance in securing Kubernetes clusters.

![image](https://github.com/user-attachments/assets/3756c365-e32c-4186-8c6d-144842db0f86)

## 1. Cluster setup Kubernetes exam updates
- **Network Security Policies**: The focus on configuring network security policies to restrict cluster-level access continues. This practice remains essential for isolating and protecting the Kubernetes cluster from unauthorized access.
- **CIS Benchmarks**: Using CIS (Center for Internet Security) benchmarks to review the security configurations of key Kubernetes components (such as etcd, kubelet, kubeapi, and kubedns) is still a critical component of this domain. Adhering to these benchmarks ensures the cluster is secured according to industry standards.
- **Ingress Setup with TLS**: One of the major updates is the emphasis on setting up ingress with Transport Layer Security (TLS). TLS is essential for encrypting data in transit and ensuring secure communication between services and clients.
- **Node Metadata Protection**: Protecting node metadata and endpoints remains a priority, with the continued recommendation to verify platform binaries before deployment. However, the previous guideline to minimize GUI access has been removed, shifting the focus towards more specific and actionable security measures.


## 2. Cluster Hardening Domain (15% Weightage, No Major Changes)

The Cluster Hardening domain remains critical in protecting the Kubernetes cluster from potential threats, with its weight unchanged at 15%.

![image](https://github.com/user-attachments/assets/55d403b2-cadf-493f-a2b4-a290e6f2ce39)

### Cluster hardening in Kubernetes
- **Restricting API Access**: This domain emphasizes restricting access to the Kubernetes API to ensure that only authorized users can interact with the cluster.
- **RBAC Policies**: The use of Role-Based Access Controls (RBAC) is encouraged to minimize exposure and ensure that users and services have only the necessary permissions.
- **Service Account Management**: Managing service accounts carefully is still critical, as they can be a potential attack vector if misconfigured.
- **Frequent Kubernetes Updates**: Keeping the Kubernetes version up to date is emphasized to avoid vulnerabilities that could be exploited in older versions.
Overall, no major changes are introduced here, but the importance of strong role-based access and API control cannot be understated.


## 3. System Hardening Domain (Weightage Reduced from 15% to 10%)

The System Hardening domain focuses on reducing the attack surface at the system level, with a slight reduction in its weight from 15% to 10%. However, the key practices remain consistent with the previous curriculum.

![image](https://github.com/user-attachments/assets/de5a980b-b3df-497a-853d-1b0bb25fac0c)

### Kubernetes system hardening
- **Minimizing OS Footprint**: Reducing the host operating system (OS) footprint to essential components remains a best practice. This helps in eliminating unnecessary software that could be exploited by attackers.
- **Least-Privilege IAM**: The previous guidance on minimizing IAM roles has been refined to emphasize the principle of least-privilege identity and access management (IAM). This ensures that users and services only have the permissions necessary to perform their tasks.
- **Restricting Network Access**: Minimizing external access to the cluster’s network reduces the risk of external attacks.
- **Kernel Hardening Tools**: The use of tools like AppArmor and seccomp continues to be a crucial practice for enforcing security policies that limit the capabilities of processes running on the system.

## 4. Minimizing Microservice Vulnerabilities (20% Weightage)

The Minimizing Microservice Vulnerabilities domain retains its weight at 20%, but several key updates have been introduced to align with modern security practices.

![image](https://github.com/user-attachments/assets/2c820ee7-69b4-43e1-95e1-5f8dc62dfce0)

### Minimizing microservice vulnerabilities

- **Pod Security Standards**: A shift in focus from OS-level security domains to using pod security standards is a significant change. Pod security standards define policies that restrict what pods can do, ensuring they operate with the least privilege required.
- **Managing Kubernetes Secrets**: Managing Kubernetes secrets securely remains essential. This involves securely storing and accessing sensitive information like API keys, tokens, and passwords.
- **Isolation Techniques**: The recommendation to use container runtime sandboxes has been expanded to a broader focus on implementing isolation techniques. This includes using multi-tenancy and sandboxed containers, among other methods.
- **Pod-to-Pod Encryption with Cilium**: Another important update is the specific mention of using Cilium for pod-to-pod encryption. Cilium enhances Kubernetes security by providing advanced networking and security policies, including robust encryption capabilities.


## 5. Supply Chain Security (20% Weightage)

The Supply Chain Security domain remains critical with a consistent weightage of 20%. Several updates have been made to incorporate modern tools and methodologies.

![image](https://github.com/user-attachments/assets/6e8e9616-10b4-4d74-96dd-ccbc0c81f679)

### Kubernetes supply chain security

- **Software Bill of Materials (SBOM)**: A significant addition is the focus on understanding the software bill of materials (SBOM). An SBOM is a detailed list of all components within a software product, helping in identifying vulnerabilities in third-party components.
- **Kubesec and KubeLinter**: Tools like Kubesec and KubeLinter have been introduced to enhance the security of Kubernetes configurations. Kubesec evaluates resource configurations for best practices, while KubeLinter analyzes YAML files and Helm charts for potential security risks.
- **CI/CD Security**: Securing the CI/CD pipeline is emphasized, ensuring that software builds and deployments are secure from vulnerabilities.

## 6. Monitoring, Logging, and Runtime Security (20% Weightage)

The Monitoring, Logging, and Runtime Security domain retains its weight at 20%, with slight rewording but no major changes. This domain is essential for maintaining the security and integrity of a Kubernetes environment through comprehensive monitoring and logging practices.

![image](https://github.com/user-attachments/assets/df9818b1-ac8d-48e6-91b2-534fa6adeffd)

### Kubernetes monitoring and logging

- **Behavioral Analytics**: Monitoring system calls, processes, and file activities at the host and container levels helps in detecting malicious activities.
- **Threat Detection**: Detecting threats in physical infrastructure, applications, networks, and data is crucial for comprehensive security.
- **Audit Logs**: The use of audit logs to monitor access and detect security breaches continues to be a key component in securing Kubernetes environments.






