Deloitte DevOps Interview — Fast Recap (Dinesh Kundo)

Quick-review notes covering every concept on the resume, organized by category.

Cloud Platforms

Azure (primary) — VMs, AKS (managed Kubernetes), Storage Accounts, Microsoft Entra ID (formerly Azure AD) for identity/SSO, NSGs (Network Security Groups) for traffic filtering between subnets/VMs.

GCP — know basic equivalents (Compute Engine ≈ VMs, GKE ≈ AKS).

AWS — CloudFormation (IaC), general service parity awareness.

Be ready to explain: why multi-cloud matters, differences between Azure/AWS/GCP services for compute, storage, networking.

Containerization & Orchestration
Docker: images vs containers, Dockerfile layers, multi-stage builds, image registries.
Kubernetes: Pods, Deployments, Services, ConfigMaps/Secrets, Ingress, scheduling, liveness/readiness probes, HPA (autoscaling).
AKS: Azure's managed K8s — node pools, cluster autoscaler, integration with Azure networking/identity.
Helm: package manager for K8s — charts, values.yaml, templating, releases, rollback (helm rollback).
Blue-green deployments: two identical environments, switch traffic all at once — zero downtime, easy rollback. (Contrast with canary/rolling updates.)
CI/CD
Jenkins: pipelines (declarative vs scripted), stages, agents, plugins, webhooks triggering builds from Bitbucket/GitHub.
Pipeline flow (narrate end-to-end): code push → build → unit tests → SonarQube scan → Docker build → Trivy scan → push to registry → Helm deploy to AKS.
Bitbucket/GitHub: branching strategy, PR-based workflow, webhook integration.
Infrastructure as Code
Terraform: providers, state file (remote state + locking), modules, plan/apply workflow, idempotency.
Azure Bicep: Azure-native alternative to ARM templates — simpler syntax, compiles to ARM JSON.
AWS CloudFormation: AWS-native IaC, stacks, templates.
Know why IaC (repeatability, version control, drift detection) and Terraform vs Bicep/CloudFormation trade-offs.
DevSecOps / Security
SonarQube: static code analysis — code smells, bugs, security hotspots, quality gates blocking merges/pipelines.
Trivy: container/image vulnerability scanning — CVEs in OS packages and dependencies.
Aikido: security tooling integrated into pipeline — be ready to describe the type of scanning it does in your own words.
IAM Policies: least-privilege principle, role-based access control (RBAC) — K8s RBAC, AWS IAM, Azure RBAC.
SSL/TLS certificates: handshake basics, cert renewal/management in pipelines.
"Shift-left security": scanning early in the pipeline instead of after deployment — most important phrase to be fluent in.
Monitoring & Observability
Prometheus: pull-based metrics collection, time-series DB, PromQL basics, exporters.
Grafana: dashboards/visualization on top of Prometheus (or other data sources).
ELK/Kibana: centralized logging — Elasticsearch (storage/search), Logstash (ingest), Kibana (visualization).
Know the difference between metrics, logs, and traces (three pillars of observability) — classic interview question.
Configuration Management
Ansible: agentless, SSH-based, YAML playbooks, idempotent tasks — contrast with Terraform (Ansible = configuration of existing servers, Terraform = provisioning infra).
Scripting
Bash/Python: have one real automation script ready to describe (health-check script, log rotation, deployment helper).
Build Tools
Maven/Gradle: Java build tools — dependency management + build lifecycle.
Projects — tight 60–90 second story for each
Current role (SurgeVector.ai): Azure infra via Terraform → Jenkins CI/CD → AKS/Helm → DevSecOps scans → monitoring stack → Entra ID/NSG security.
AFTRA THE FUND: microservices, K8s autoscaling + zero-downtime deploys, full observability stack, Aikido security for payment data, disaster recovery/backup strategy — be ready to explain DR specifics (RTO/RPO, backup frequency, failover approach).
Certifications
AZ-104 (Azure Administrator Associate) — basic Azure admin questions (resource groups, subscriptions, RBAC).
GCP Professional Cloud Architect — advanced-level cert; be ready to explain one GCP architecture concept.
Likely Deloitte Interview Angles
Real incidents handled (production outage, failed deployment, security vulnerability caught)
Trade-off reasoning (Terraform vs Bicep, blue-green vs canary)
Basic conceptual clarity over tool-name memorization

Prep priority: 2–3 STAR-format stories (Situation/Task/Action/Result) from current role + AFTRA project.
