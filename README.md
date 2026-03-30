<p align="center">
  <img width="360" src="kubernetes-security-specialist-logo.png">
</p>
<p align="center">
  <img src="https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat">
  <img src="https://img.shields.io/badge/status-preview-brightgreen?style=flat">
  <img src="https://img.shields.io/github/issues-raw/ijelliti/CKSS-Certified-Kubernetes-Security-Specialist?style=flat">
  
  <img src="https://img.shields.io/github/license/ijelliti/CKSS-Certified-Kubernetes-Security-Specialist?style=flat">
  <img src="https://img.shields.io/github/stars/ijelliti/CKSS-Certified-Kubernetes-Security-Specialist?style=social">
  <img src="https://img.shields.io/github/forks/ijelliti/CKSS-Certified-Kubernetes-Security-Specialist?style=social">
</p>


# Certified Kubernetes Security Specialist - CKSS
This repository is a collection of resources to prepare for the Certified Kubernetes Security Specialist (CKSS) exam.
> The given references and links below are just assumptions and ideas around the [CKSS curriculum](https://github.com/cncf/curriculum/blob/master/CKS_Curriculum_%20v1.19.pdf).

## CKS Overview
The Kubernetes Security Specialist (CKS) certification ensure that the holder has the skills, knowledge, and competence on a broad range of best practices for securing container-based applications and Kubernetes platforms during build, deployment and runtime.

The certification is generally available to take from [here](https://training.linuxfoundation.org/certification/certified-kubernetes-security-specialist/) as anounced during the KubeCon NA20

## CKS Outline
The CKS test will be online, proctored and performance-based with 15-20 hands-on performance based tasks, and candidates have 2 hours to complete the exam tasks.

From the CKS Exam Curriculum repository, The exam will test domains and competencies including:
1. **Cluster Setup (15%)**: Best practice configuration to control the environment's access, rights and platform conformity.
2. **Cluster Hardening (15%)**: Protecting K8s API and utilize RBAC.
3. **System Hardening (10%)**: Improve the security of OS & Network; restrict access through IAM
4. **Minimize Microservice Vulnerabilities (20%)**: Utilizing on K8s various mechanisms to isolate, protect and control workload.
5. **Supply Chain Security (20%)**: Container oriented security, trusted resources, optimized container images, CVE scanning.
6. **Monitoring, Logging, and Runtime Security (20%)**: Analyse and detect threads.

# CKS Exam Preparation

In order to take the CKS exam, you must have **Valid CKA certification** prior to attempting the CKS exam to demonstrate you possess sufficient Kubernetes expertise.
A first good starting point for securing Kubernetes is the Task section [**Securing a Cluster**](https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/) of the official K8s documentation.
The exam will be based on **the version of Kubernetes as specified by the CKS Curriculum doc in the [CNCF Curriculum repository](https://github.com/cncf/curriculum)**

# Allowed resources to access during the CKS exam:
According to the [LF docs](https://docs.linuxfoundation.org/tc-docs/certification/certification-resources-allowed#certified-kubernetes-security-specialist-cks), during the CKS exam the candidates may:
- review the Exam content instructions that are presented in the command line terminal.
- review Documents installed by the distribution (i.e. /usr/share and its subdirectories)
- use the Firefox browser in the exam environment in order to access 
  - **Kubernetes Documentation:**
    - https://kubernetes.io/docs/ and their subdomains
    - https://kubernetes.io/blog/ and their subdomains
    
    This includes all available language translations of these pages (e.g. https://kubernetes.io/zh/docs/)
  - **Tools**:
    - Falco documentation https://falco.org/docs/
    - Bom documentation https://kubernetes-sigs.github.io/bom/cli-reference/
    - etcd documentation https://etcd.io/docs/
    - NGINX Ingress Controller Documentation https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/
    - Cilium Documentation https://docs.cilium.io/en/stable
    - Istio Documentation https://istio.io/latest/docs/
    
  The allowed sites above may contain links that point to external sites. It is the responsibility of the candidate not to click any links to navigate to a domain that is not allowed but the exam environment is typically configured to block access to disallowed domains.

## Cluster Setup (15%)
<details><summary>Use Network security policies to restrict cluster level access</summary>
  
#### Allowed Ressources
* [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies)
* [Securing a Cluster](https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/)
* [Declare Network Policy](https://kubernetes.io/docs/tasks/administer-cluster/declare-network-policy/)
* [Enforcing Network Policies in Kubernetes](https://kubernetes.io/blog/2017/10/enforcing-network-policies-in-kubernetes/)
#### 3rd Party Ressources
* [Get started with Kubernetes network policy](https://docs.projectcalico.org/security/kubernetes-network-policy)
* [kubernetes-network-policy-recipes](https://github.com/ahmetb/kubernetes-network-policy-recipes)
* [Kubernetes Network Policies Best Practices](https://snyk.io/blog/kubernetes-network-policy-best-practices/)
</details>

<details><summary>Use CIS benchmark to review the security configuration of Kubernetes components (etcd, kubelet, kubedns, kubeapi)</summary>
  
#### 3rd Party Ressources
* [CIS benchmark for Kubernetes](https://www.cisecurity.org/benchmark/kubernetes/)
* [What is Center for Internet Security (CIS) Benchmarks](https://docs.microsoft.com/en-us/microsoft-365/compliance/offering-cis-benchmark)
* [Kube-bench](https://github.com/aquasecurity/kube-bench#running-kube-bench): A tool for running Kubernetes CIS Benchmark tests
* [GKE: CIS Benchmarks for etcd & kubelet](https://cloud.google.com/kubernetes-engine/docs/concepts/cis-benchmarks#default-values) 
</summary>
</details>

<details><summary>Properly set up Ingress objects with TLS</summary>

#### Allowed Ressources
* [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/)
* [Ingress Controllers](https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/)
* [NGINX Configuration](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/)
* [secure an Ingress by specifying a Secret that contains a TLS private key and certificate](https://kubernetes.io/docs/concepts/services-networking/ingress/#tls)
#### 3rd Party Ressources
* [How to deploy NGINX Ingress Controller](https://github.com/kubernetes/ingress-nginx/blob/master/docs/deploy/index.md)
* [TLS/HTTPS](https://github.com/kubernetes/ingress-nginx/blob/master/docs/user-guide/tls.md)
</details>

<details><summary>Protect node metadata and endpoints</summary>

#### Allowed Ressources
* [Restricting cloud metadata API access](https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/#restricting-cloud-metadata-api-access)
* [Kubelet authentication/authorization](https://kubernetes.io/docs/reference/access-authn-authz/kubelet-authn-authz/)
#### 3rd Party Ressources
* [Setting up secure endpoints in Kubernetes](https://blog.cloud66.com/setting-up-secure-endpoints-in-kubernetes/)
* [GKE Protecting cluster metadata](https://cloud.google.com/kubernetes-engine/docs/how-to/protecting-cluster-metadata)
* [Retrieving EC2 instance metadata](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instancedata-data-retrieval.html)
* [EC2 Instance user data](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html)
</details>

<details><summary>Verify platform binaries before deploying</summary>

#### Allowed Ressources
* [Kubernetes Binaries](https://kubernetes.io/releases/download/#binaries)
* [Verify Signed Kubernetes Artifacts](https://kubernetes.io/docs/tasks/administer-cluster/verify-signed-artifacts/)
</details>

## Cluster Hardening (15%)
<details><summary>Use Role Based Access Controls to minimize exposure</summary>

#### Allowed Ressources
* [Using RBAC Authorization](https://kubernetes.io/docs/reference/access-authn-authz/rbac/)
* [Authorization modes for Kubernetes API server](https://kubernetes.io/docs/reference/access-authn-authz/authorization/#authorization-modules)
#### 3rd Party Ressources
* [Site for Kubernetes RBAC](https://rbac.dev/)
* [Understand Role-Based Access Control in Kubernetes](https://www.youtube.com/watch?v=G3R24JSlGjY)
* [RBAC Study Guide](https://github.com/David-VTUK/CKA-StudyGuide/blob/master/cka-study-guide/docs/revision-topics/01-architcture-installation-configuration.md)
</details>

<details><summary>Exercise caution in using service accounts e.g. disable defaults, minimize permissions on newly created ones</summary>
  
#### Allowed Ressources
* [Managing Service Accounts](https://kubernetes.io/docs/reference/access-authn-authz/service-accounts-admin/)
* [Default roles and role bindings](https://kubernetes.io/docs/reference/access-authn-authz/rbac/#default-roles-and-role-bindings)
* [Authorization Modes](https://kubernetes.io/docs/reference/access-authn-authz/authorization/#authorization-modules)
* [Configure Service Accounts for Pods](https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/)
#### 3rd Party Ressources
* [Kubernetes should not mount default service account credentials by default](https://github.com/kubernetes/kubernetes/issues/57601)
* [Kubernetes: Creating Service Accounts and Kubeconfigs](https://docs.armory.io/docs/armory-admin/manual-service-account/)
* [Kubernetes Access Control: Exploring Service Accounts](https://thenewstack.io/kubernetes-access-control-exploring-service-accounts/)
* [Disable default service account by deployments in Kubernetes](https://stackoverflow.com/questions/52583497/how-to-disable-the-use-of-a-default-service-account-by-a-statefulset-deployments)
* [Securing Kubernetes Clusters by Eliminating Risky Permissions](https://www.cyberark.com/resources/threat-research-blog/securing-kubernetes-clusters-by-eliminating-risky-permissions)
* [Understand Role Based Access Control in Kubernetes](https://www.youtube.com/watch?v=G3R24JSlGjY)
* [Cloud Native Short Take - Kubernetes: Roles-based Access Control RBAC](https://youtu.be/bFdK-zv-oJk)
</details>

<details><summary>Restrict access to Kubernetes API</summary>

#### Allowed Ressources
* [Controlling Access to the Kubernetes API](https://kubernetes.io/docs/reference/access-authn-authz/controlling-access/)
* [Certificate Signing Requests: Create Normal User](https://kubernetes.io/docs/reference/access-authn-authz/certificate-signing-requests/#normal-user)
* [Generate cluster certificates (easyrsa, openssl or cfssl)](https://kubernetes.io/docs/concepts/cluster-administration/certificates/)
#### 3rd Party Ressources
* [GKE: Hardening your cluster's security](https://cloud.google.com/anthos/gke/docs/on-prem/how-to/hardening-your-cluster)
* [Kubernetes RBAC and TLS certificates – Kubernetes security guide](https://sysdig.com/blog/kubernetes-security-rbac-tls/)
* [Securing Your Kubernetes API Server](https://tufin.medium.com/protecting-your-kubernetes-api-server-5eefeea4cf8a)
</details>

<details><summary>Upgrade Kubernetes to avoid vulnerabilities</summary>
  
#### Allowed Ressources
* [kubeadm upgrade](https://kubernetes.io/docs/reference/setup-tools/kubeadm/kubeadm-upgrade/)
</details>

## System Hardening (10%)
<details><summary>Minimize host OS footprint (reduce attack surface)</summary>

#### Allowed Ressources
* [Preventing containers from loading unwanted kernel modules](https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/#preventing-containers-from-loading-unwanted-kernel-modules)
#### 3rd Party Ressources
* [Reduce Kubernetes Attack Surfaces](https://blog.sonatype.com/kubesecops-kubernetes-security-practices-you-should-follow#:~:text=Reduce%20Kubernetes%20Attack%20Surfaces)
* [CIS Benchmark Ubuntu Linux](https://www.cisecurity.org/benchmark/ubuntu_linux/)
* [CIS Benchmark RedHat](https://www.cisecurity.org/benchmark/red_hat_linux/)
* [CIS Benchmark Debian](https://www.cisecurity.org/benchmark/debian_linux/)
* [CIS Benchmark SUSE](https://www.cisecurity.org/benchmark/suse_linux/)
* [CIS Benchmark Oracle](https://www.cisecurity.org/benchmark/oracle_linux/)
</details>

<details><summary>Using least-privilege identity and access management</summary>

#### 3rd Party Ressources
* [What is the Principle of Least Privilege (POLP)?](https://digitalguardian.com/blog/what-principle-least-privilege-polp-best-practice-information-security-and-compliance)
* [IAM Grant least privilege](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#grant-least-privilege)
</details>

<details><summary>Minimize external access to the network</summary>

#### Allowed Ressources
* [K8s quotas (services.loadbalancers)](https://kubernetes.io/docs/concepts/policy/resource-quotas/)
#### 3rd Party Ressources
* [Admission control plugin: ResourceQuota](https://github.com/kubernetes/design-proposals-archive/blob/main/resource-management/admission_control_resource_quota.md)
* [Secure hosts with OS-level firewall (ufw)](https://help.replicated.com/community/t/managing-firewalls-with-ufw-on-kubernetes/230)
* [Configure firewall with ufw](https://www.linode.com/docs/security/firewalls/configure-firewall-with-ufw/)
* [Use security groups to secure network (Azure)](https://docs.microsoft.com/en-us/azure/aks/concepts-security#azure-network-security-groups)
* [Amazon EKS security group considerations](https://docs.aws.amazon.com/eks/latest/userguide/sec-group-reqs.html)
* [Amazon EC2 security groups for Linux instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-security-groups.html)
</details>

<details><summary>Appropriately use kernel hardening tools such as AppArmor, seccomp</summary>

#### Allowed Ressources
* [Restrict a Container's Access to Resources with AppArmor](https://kubernetes.io/docs/tutorials/clusters/apparmor/)
* [Restrict a Container's Syscalls with Seccomp](https://kubernetes.io/docs/tutorials/clusters/seccomp/)
#### 3rd Party Ressources
* [NSA, CISA Kubernetes Hardening Guide](https://media.defense.gov/2022/Aug/29/2003066362/-1/-1/0/CTR_KUBERNETES_HARDENING_GUIDANCE_1.2_20220829.PDF)
* [Container Security: Fundamental Technology Concepts that Protect Containerized Application by Liz Rice](https://cdn2.hubspot.net/hubfs/1665891/Assets/Container%20Security%20by%20Liz%20Rice%20-%20OReilly%20Apr%202020.pdf)
</details>

## Minimize Microservice Vulnerabilities (20%)
<details><summary>Use appropriate pod security standards</summary>

#### Allowed Ressources
* [Pod Security Standards](https://kubernetes.io/docs/concepts/security/pod-security-standards/)
* [Pod Security Admission](https://kubernetes.io/docs/concepts/security/pod-security-admission/)
* [Configure a Security Context for a Pod or Container](https://kubernetes.io/docs/tasks/configure-pod-container/security-context/)
* [OPA Gatekeeper: Policy and Governance for Kubernetes](https://kubernetes.io/blog/2019/08/06/opa-gatekeeper-policy-and-governance-for-kubernetes/)

#### 3rd Party Ressources
* [Kubernetes security context, security policy, and network policy – Kubernetes security guide (part 2)](https://sysdig.com/blog/kubernetes-security-psp-network-policy/)
* [Open Policy Agent Introduction](https://www.youtube.com/watch?v=Yup1FUc2Qn0)
* [Enforce policies on Kubernetes objects with OPA](https://www.openpolicyagent.org/docs/kubernetes)
</details>

<details><summary>Manage kubernetes secrets</summary>

#### Allowed Ressources
* [Kubernetes Secrets](https://kubernetes.io/docs/concepts/configuration/secret/)
* [Encrypting Secret Data at Rest](https://kubernetes.io/docs/tasks/administer-cluster/encrypt-data/)
* [Using a KMS provider for data encryption](https://kubernetes.io/docs/tasks/administer-cluster/kms-provider/)
#### 3rd Party Ressources
* [Secrets Store CSI driver](https://github.com/kubernetes-sigs/secrets-store-csi-driver)
* [How to Manage Secrets in Kubernetes](https://spacelift.io/blog/kubernetes-secrets)
</details>

<details><summary>Understand and implement isolation techniques (multi-tenancy, sandboxed containers, etc.)</summary>

#### Allowed Ressources
* [container runtime](https://kubernetes.io/docs/concepts/containers/runtime-class/)
* [Assigning Pods to Nodes](https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/)
#### 3rd Party Ressources
* [container runtime sandboxes examples](https://github.com/kubernetes/enhancements/blob/master/keps/sig-node/585-runtime-class/README.md#examples)
* [What is gVisor?](https://gvisor.dev/docs/)
* [Cluster multi-tenancy](https://cloud.google.com/kubernetes-engine/docs/concepts/multitenancy-overview)
* [Use gVisor to run Kubernetes pods](https://gvisor.dev/docs/user_guide/quick_start/kubernetes/)
* [Implementing secure Containers using Google’s gVisor](https://thenewstack.io/how-to-implement-secure-containers-using-googles-gvisor/)
* [Kata containers and Kubernetes: How they fit together?](https://platform9.com/blog/kata-containers-docker-and-kubernetes-how-they-all-fit-together/)
* [How to use Kata Containers with Kubernetes?](https://github.com/kata-containers/documentation/blob/master/how-to/how-to-use-k8s-with-cri-containerd-and-kata.md)
</details>

<details><summary>Implement Pod-to-Pod encryption (Cilium, Istio)</summary>
  
#### Allowed Ressources
* [Manage TLS Certificates in a Cluster](https://kubernetes.io/docs/tasks/tls/managing-tls-in-a-cluster/)
* [Cilium Network Policy](https://docs.cilium.io/en/stable/security/policy/#network-policy)
* [Istio PeerAuthentication](https://istio.io/latest/docs/reference/config/security/peer_authentication/)
* [Using Istio to improve end-to-end security](https://istio.io/latest/blog/2017/0.1-auth/)
#### 3rd Party Ressources
* [A Kubernetes engineer’s guide to mTLS](https://www.buoyant.io/mtls-guide)
* [Secure communication between services in Istio with mutual TLS](https://developer.ibm.com/tutorials/istio-security-mtls/)
* [Mutual TLS Authentication (mTLS) De-Mystified](https://codeburst.io/mutual-tls-authentication-mtls-de-mystified-11fa2a52e9cf)
* [Traffic encryption using mTLS](https://www.istioworkshop.io/11-security/01-mtls/)
</details>

## Supply Chain Security (20%)

<details><summary>Minimize base image footprint</summary>

#### 3rd Party Ressources
* [Why build small container images in Kubernetes](https://cloud.google.com/blog/products/gcp/kubernetes-best-practices-how-and-why-to-build-small-container-images)
* [7 best practices for building containers](https://cloud.google.com/blog/products/gcp/7-best-practices-for-building-containers)
* [distroless containers](https://github.com/GoogleContainerTools/distroless)
* [Docker Hardened Images](https://www.docker.com/products/hardened-images/)
* [SlimToolkit](https://slimtoolkit.org/)
* [Docker multi-stage builds](https://docs.docker.com/develop/develop-images/multistage-build/)
* [Tips to Reduce Docker Image Sizes](https://hackernoon.com/tips-to-reduce-docker-image-sizes-876095da3b34)
* [3 simple tricks for smaller Docker images](https://learnk8s.io/blog/smaller-docker-images)
* [Docker multi-stage build with Go](https://youtu.be/wQDkLxj9ALs)
</details>

<details><summary>Secure your supply chain (permitted registries, sign and validate artifacts, etc.)</summary>

#### Allowed Ressources
* [Using Admission Controllers](https://kubernetes.io/docs/reference/access-authn-authz/admission-controllers/)
* [Dynamic Admission Control](https://kubernetes.io/docs/reference/access-authn-authz/extensible-admission-controllers/)
* [A Guide to Kubernetes Admission Controllers](https://kubernetes.io/blog/2019/03/21/a-guide-to-kubernetes-admission-controllers/)
#### 3rd Party Ressources
* [Ensure images only from approved sources are run](https://github.com/kubernetes/kubernetes/issues/22888)
* [How to reject docker registries in Kubernetes?](https://stackoverflow.com/questions/54463125/how-to-reject-docker-registries-in-kubernetes)
* [Restrict pulling images from Registry](https://www.openpolicyagent.org/docs/kubernetes)
* [Sign and verify container images with Sigstore Cosign](https://docs.sigstore.dev/cosign/)
</details>

<details><summary>Perform static analysis of user workloads and container images (e.g. Kubesec, KubeLinter)</summary>

#### Allowed Ressources
* [11 Ways (Not) to Get Hacked: statically-analyse-yaml](https://kubernetes.io/blog/2018/07/18/11-ways-not-to-get-hacked/#7-statically-analyse-yaml)

#### 3rd Party Ressources
* [Trivy](https://github.com/aquasecurity/trivy)
* [Static analysis with KubeLinter](https://docs.kubelinter.io/)
* [Static analysis with Kube-score](https://kube-score.com/)
* [kubesec](https://kubesec.io/)
* [Kubernetes static code analysis with Checkov](https://www.checkov.io/)
</details>

<details><summary>Understand your supply chain (e.g. SBOM, CI/CD, artifact repositories)</summary>
  
#### Allowed Ressources
* [Check artifacts against SPDX manifests with bom](https://kubernetes-sigs.github.io/bom/cli-reference/bom_validate/)
#### 3rd Party Ressources
* [What is a software bill of materials (SBOM)?](https://github.com/resources/articles/what-is-an-sbom-software-bill-of-materials)
* [Linux Foundation: SPDX tools](https://spdx.dev/use/spdx-tools/)
</details>

## Monitoring, Logging and Runtime Security (20%)

<details><summary>Perform behavioral analytics to detect malicious activities</summary>

#### Allowed Ressources
* [Restrict a Container's Syscalls with Seccomp](https://kubernetes.io/docs/tutorials/clusters/seccomp/)
* [An Introduction to Kubernetes Security using Falco](https://falco.org/blog/intro-k8s-security-monitoring/)
* [Falco Rules](https://falco.org/docs/reference/rules/)
#### 3rd Party Ressources
* [Kubernetes Security monitoring at scale](https://medium.com/@SkyscannerEng/kubernetes-security-monitoring-at-scale-with-sysdig-falco-a60cfdb0f67a)
</details>

<details><summary>Detect threats within physical infrastructure, apps, networks, data, users and workloads</summary>

#### 3rd Party Ressources
* [Common Kubernetes config security threats](https://www.cncf.io/blog/2020/08/07/common-kubernetes-config-security-threats/)
* [A guidance on Kubernetes threat modeling](https://www.trendmicro.com/vinfo/us/security/news/virtualization-and-cloud/guidance-on-kubernetes-threat-modeling)
* [A Deep Dive Into Kubernetes Threat Modeling](https://www.trendmicro.com/vinfo/us/security/news/security-technology/a-deep-dive-into-kubernetes-threat-modeling)
* [Threat matrix for Kubernetes](https://www.microsoft.com/security/blog/2020/04/02/attack-matrix-kubernetes/)
</details>

<details><summary>Investigate and identify phases of attack and bad actors within the environment</summary>

#### 3rd Party Ressources
* [Anatomy of a Kubernetes attack – How untrusted Docker images fails us](https://www.optiv.com/explore-optiv-insights/source-zero/anatomy-kubernetes-attack-how-untrusted-docker-images-fail-us)
* [The seven phases of a cyber attack](https://www.dnv.com/cyber/insights/articles/recognizing-the-seven-stages-of-a-cyber-attack/)
* [Threat matrix for Kubernetes](https://www.microsoft.com/security/blog/2020/04/02/attack-matrix-kubernetes/)
* [MITRE ATT&CK framework for container runtime security with Falco](https://sysdig.com/blog/mitre-attck-framework-for-container-runtime-security-with-sysdig-falco/)
* [Mitigating Kubernetes attacks](https://www.youtube.com/watch?v=HWv8ZKLCawM)
</details>

<details><summary>Ensure immutability of containers at runtime</summary>

#### Allowed Ressources
* ["ReadOnlyRootFilesystem" (securityContext)](https://kubernetes.io/docs/tasks/configure-pod-container/security-context/)
* ["readOnly" volume mount](https://kubernetes.io/docs/concepts/storage/volumes/#read-only-mounts)
* [Principles of Container-based Application Design](https://kubernetes.io/blog/2018/03/principles-of-container-app-design/)
#### 3rd Party Ressources
* [Leverage Kubernetes to ensure that containers are immutable](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux_atomic_host/7/html/container_security_guide/keeping_containers_fresh_and_updateable#leveraging_kubernetes_and_openshift_to_ensure_that_containers_are_immutable)
* [Why I think we should all use immutable Docker images](https://medium.com/sroze/why-i-think-we-should-all-use-immutable-docker-images-9f4fdcb5212f)
</details>

<details><summary>Use Kubernetes audit logs to monitor access</summary>

#### Allowed Ressources
* [Kubernetes Audit](https://kubernetes.io/docs/tasks/debug-application-cluster/audit/)
#### 3rd Party Ressources
* [Kubernetes Audit logging](https://docs.sysdig.com/en/kubernetes-audit-logging.html)
* [How to monitor Kubernetes audit logs?](https://www.datadoghq.com/blog/monitor-kubernetes-audit-logs/)
* [Kubernetes Audit: Making Log Auditing a Viable Practice Again](https://www.cncf.io/blog/2019/12/03/kubernetes-audit-making-log-auditing-a-viable-practice-again/)
</details>

# Related Kubernetes security resources
* [FREE CKS self-study course](https://rx-m.com/cks-self-study-course/)
* [Kubernetes Security Essentials (LFS260) video course](https://training.linuxfoundation.org/training/kubernetes-security-essentials-lfs260/)
* [Cloud Native Security Tutorial](https://tutorial.kubernetes-security.info/)
* [Killer Shell CKS Simulator](https://killer.sh/cks)
* [Killer Coda CKS Simulator](https://killercoda.com/killer-shell-cks)
* [Sysdig Kubernetes Security Guide](https://www.sysdig.com/s-kubernetes-security-guide)
* [Kubernetes Security Best Practices - Ian Lewis, Google](https://youtu.be/wqsUfvRyYpw)
* [Kubernetes security concepts and demos](https://youtu.be/VjlvS-qiz_U)
* [Tutorial: Getting Started With Cloud Native Security - Liz Rice, Aqua Security & Michael Hausenblas](https://youtu.be/MisS3wSds40)
* [11 Ways (Not) to Get Hacked](https://kubernetes.io/blog/2018/07/18/11-ways-not-to-get-hacked/)
* [Kubernetes Goat](https://github.com/madhuakula/kubernetes-goat)
* [Kubernetes CTF on vagrant environment (archived)](https://github.com/NodyHub/k8s-ctf-rocks)
* [CKS 5-day Boot Camp (live, instructor-led)](https://rx-m.com/training/certified-kubernetes-security-specialist-cks-boot-camp/)
* [CKS 1-day Exam Prep (live, instructor-led)](https://rx-m.com/training/certified-kubernetes-security-specialist-cks-exam-prep/)
* [Certified Kubernetes Security Specialist 2026 video course](https://www.udemy.com/course/certified-kubernetes-security-specialist-certification/)
* [NSA/CISA Kubernetes Hardening Guidance 08/2022](https://media.defense.gov/2022/Aug/29/2003066362/-1/-1/0/CTR_KUBERNETES_HARDENING_GUIDANCE_1.2_20220829.PDF)
### White Papers
* [CNCF cloud-native security white paper v2 May 2022](https://github.com/cncf/tag-security/blob/main/community/resources/security-whitepaper/v2/CNCF_cloud-native-security-whitepaper-May2022-v2.pdf)

# Keep Updating
* LIVING DOCUMENT - I WILL UPDATE IT FREQUENTLY WHEN I HAVE NEW INFORMATIONS
* PRs are always welcome so star, fork and contribute
  * please make a pull request if you would like to add or update 


Ibrahim Jelliti © 2020

