## Learning Path

| Project | Subject | Main outcome |
| --- | --- | --- |
| 00 | [Virtualization](Beginner-Project00-Virtualization/README.md) | Build and secure a Linux virtual machine. |
| 01 | [Networking Fundamentals](Beginner-Project01-Networking/README.md) | Connect two machines and understand IP, DNS, ports and firewalls. |
| 02 | [Web Server and TLS](Beginner-Project02-Web-Server-and-TLS/README.md) | Host secure websites behind NGINX. |
| 03 | [Vagrant Provisioning](Beginner-Project03-Vagrant-Provisioning/README.md) | Rebuild the lab automatically with one command. |
| 04 | [Ansible](Beginner-Project04-Ansible/README.md) | Configure several machines with idempotent playbooks. |
| 05 | [Containerization](Beginner-Project05-Containerization/README.md) | Run a multi-service application with Docker Compose. |
| 06 | [Backup and Recovery](Beginner-Project06-Backup-and-Recovery/README.md) | Back up, delete and successfully restore application data. |
| 07 | [Monitoring](Beginner-Project07-Monitoring/README.md) | Detect failures with metrics, dashboards and alerts. |
| 08 | [Kubernetes](Beginner-Project08-Kubernetes/README.md) | Move the containerized application to K3s or K3d. |
| 09 | [Terraform and Vagrant VMs](Beginner-Project09-Local-Terraform/README.md) | Build the same local VM lab with Vagrant and Terraform. |
| 10 | [CI/CD and Observability](Beginner-Project10-CICD-and-Observability/README.md) | Test, release, observe and roll back an application. |

## How the Track Works

- Complete the projects in order.
- Keep every project in its own Git repository unless the instructor says otherwise.
- Make small, meaningful commits.
- Never commit passwords, tokens, private keys, real `.env` files or Terraform state.
- Document commands, design choices, tests and problems in a project README.
- A project passes only when the student can demonstrate it and explain how it works.

## Standard Submission

Every project submission should contain:

- A `README.md` with setup, usage, testing and cleanup instructions.
- All scripts and configuration needed to reproduce the result.
- A `.gitignore` that protects local and sensitive files.
- Evidence of the required tests.
- A short section explaining challenges and lessons learned.

## Curriculum Levels

- Projects 00-04: beginner foundations.
- Projects 05-07: beginner DevOps operations.
- Projects 08-10: beginner-to-intermediate platform engineering.


Once you finish beginner projects , you have to start an advanced project.

<p align="center">
  <img src="images/next-level.png" alt="Hit the next level" width="600">
</p>


## Advanced Team Capstones

Advanced projects are semester projects for teams. A team normally selects one project; these projects are not a sequence that every student must complete.

| Project | Subject | Main outcome |
| --- | --- | --- |
| 01 | [CI/CD with Cloud Infrastructure as Code](Advanced-Project01-CICD-Cloud-IaC/README.md) | Build a secure cloud delivery pipeline with Terraform and immutable releases. |
| 02 | [Observability and SRE](Advanced-Project02-Observability-SRE/README.md) | Diagnose failures by connecting metrics, logs, traces and SLOs. |
| 03 | [GitOps and Progressive Delivery](Advanced-Project03-GitOps-Progressive-Delivery/README.md) | Deliver canary or blue-green releases from Git with metric-based rollback. |
| 04 | [Mini Kubernetes PaaS](Advanced-Project04-Mini-Kubernetes-PaaS/README.md) | Build a safe internal platform for deploying approved applications. |
| 05 | [Knative Serverless Platform](Advanced-Project05-Knative-Serverless/README.md) | Operate scale-to-zero HTTP services and event-driven workloads. |
| 06 | [FinOps with OpenCost](Advanced-Project06-FinOps-OpenCost/README.md) | Allocate Kubernetes cost and produce budget and rightsizing recommendations. |
| 07 | [OpenBao Encryption Service](Advanced-Project07-OpenBao-Encryption-Service/README.md) | Provide identity-based encryption without exposing raw keys. |
| 08 | [Kubernetes Runtime Security](Advanced-Project08-Kubernetes-Runtime-Security/README.md) | Combine admission policy with eBPF runtime detection. |
| 09 | [Software Supply Chain Security](Advanced-Project09-Software-Supply-Chain-Security/README.md) | Scan, inventory, sign and verify software artifacts before deployment. |
| 10 | [Kubernetes Backup and Disaster Recovery](Advanced-Project10-Kubernetes-Backup-DR/README.md) | Prove stateful application recovery against defined RPO and RTO targets. |
| 11 | [Open Data Lake Platform](Advanced-Project11-Data-Lake/README.md) | Stream, store and query analytical data using open components. |
| 12 | [SRE Incident Game Day](Advanced-Project12-SRE-Incident-Game-Day/README.md) | Practice measurable incident response and blameless improvement. |

## Advanced Project Rules

- Teams should contain 2-4 students unless the project says otherwise.
- Every team must define member roles, milestones and weekly evidence.
- Cloud projects require an instructor-approved account, maximum budget and cleanup plan.
- Students must use synthetic data and must not process personal.
- A project passes only when the team demonstrates behavior, failure handling and cleanup.
- Optional extensions are evaluated only after all mandatory milestones pass.

Have Fun :D
