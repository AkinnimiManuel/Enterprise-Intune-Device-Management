# Enterprise Intune Device Management

> A hands-on Microsoft Intune enterprise lab for managing Windows devices through Microsoft Entra ID and Microsoft Intune.

## Overview

**Enterprise Intune Device Management** is the second project in the Project Zero enterprise Microsoft 365 lab series.

The project builds a practical endpoint-management environment using Microsoft Intune, Microsoft Entra ID, VMware Workstation, and four Windows 11 virtual machines. The lab is designed to demonstrate how an organization can centrally enroll, configure, secure, monitor, and manage Windows devices from Microsoft Intune.

This project builds on the identity, Microsoft 365 tenant, licensing, security, and Conditional Access foundation established in the previous **Enterprise Microsoft 365 Deployment** project.

## 📚 Project Documentation

Detailed implementation notes, configuration decisions, procedures, and validation results are maintained in the [`docs`](./docs) directory.

| Phase | Documentation | Status |
|---|---|---|
| 01 | [`Project Planning`](./docs/01-Project-Planning.md) | ✅ Completed |
| 02 | [`Intune Configuration`](./docs/02-Intune-Configuration.md) | ✅ Conpleted |
| 03 | [`Device Enrollment`](./docs/03-Device-Enrollment.md) | ✅ Completed |
| 04 | [`Windows Autopilot`](./docs/04-Windows-Autopilot.md) | ✅ Completed |
| 05 | [`Device Configuration`](./docs/05-Device-Configuration.md) | ⌛ In-Progress |
| 06 | [`Compliance Policies`](./docs/06-Compliance-Policies.md) | Planned |
| 07 | [`Conditional Access Integration`](./docs/07-Conditional-Access-Integration.md) | Planned |
| 08 | [`Endpoint Security`](./docs/08-Endpoint-Security.md) | Planned |
| 09 | [`Application Management`](./docs/09-Application-Management.md) | Planned |
| 10 | [`Device Management`](./docs/10-Device-Management.md) | Planned |
| 11 | [`Monitoring and Operations`](./docs/11-Monitoring-and-Operations.md) | Planned |


## Objectives

- Build an enterprise-style Microsoft Intune management environment.
- Enroll and manage Windows 11 devices through Microsoft Intune.
- Configure Windows devices using Intune configuration profiles.
- Establish device compliance requirements.
- Integrate Intune compliance with Microsoft Entra Conditional Access.
- Implement endpoint security controls through Intune.
- Deploy and manage applications.
- Manage Windows updates and device lifecycle operations.
- Monitor device health, compliance, configuration, and management status.
- Document the environment so the implementation can be reproduced and extended.

## Lab Environment

The physical environment consists of one laptop running VMware Workstation with three Windows 11 virtual machines.

| Device | Assigned User | Role |
|---|---|---|
| `PRX-WIN11-001` | Damilola Ogunwole | COO |
| `PRX-WIN11-002` | Stefan Akinnimi | IT Administrator / Global Administrator |
| `PRX-WIN11-003` | Jane Smith | HR Manager |
| `PRX-WIN11-004` | Micheal Brown | Operations Manager |

### Architecture

```text
                                    Microsoft 365 Tenant
                                            |
                                +-----------+-----------+
                                |                       |
                          Microsoft Entra ID       Microsoft Intune
                                |                       |
                                +-----------+-----------+
                                            |
                                    Managed Windows 11
                                          Devices
                                            |
              +-----------------+-------------------------------------+
              |                 |                 |                   |
              v                 v                 v                   v
       PRX-WIN11-001     PRX-WIN11-002     PRX-WIN11-003          PRX-WIN11-004
         Damilola            Stefan             Jane                Micheal
            COO            IT Administrator     HR Manager         Operations Manager
```

## Project Scope

The project covers the following core Intune capabilities:

| Area | Scope |
|---|---|
| Intune Configuration | Tenant configuration, enrollment settings, groups, RBAC and management foundations |
| Device Enrollment | Windows enrollment and Microsoft Entra joined device management |
| Windows Autopilot | Device provisioning and deployment configuration |
| Device Configuration | Configuration profiles and Windows device settings |
| Compliance Policies | Device compliance requirements and actions for non-compliance |
| Conditional Access | Integration between device compliance and Microsoft Entra access controls |
| Endpoint Security | Defender, Firewall, BitLocker, Attack Surface Reduction and related security controls |
| Application Management | Deployment and management of required business applications |
| Device Management | Device actions, updates, inventory and lifecycle operations |
| Monitoring & Operations | Reporting, troubleshooting, auditing and operational management |

## Repository Structure

```text
Enterprise-Intune-Device-Management/
|
+-- README.md
|
+-- docs/
|   +-- 01-Project-Planning.md
|   +-- 02-Intune-Configuration.md
|   +-- 03-Device-Enrollment.md
|   +-- 04-Windows-Autopilot.md
|   +-- 05-Device-Configuration.md
|   +-- 06-Compliance-Policies.md
|   +-- 07-Conditional-Access-Integration.md
|   +-- 08-Endpoint-Security.md
|   +-- 09-Application-Management.md
|   +-- 10-Device-Management.md
|   +-- 11-Monitoring-and-Operations.md
|
+-- scripts/
|   +-- README.md
|
+-- diagrams/
    +-- Intune-Architecture.png
```

## Implementation Approach

The project follows the device lifecycle from enrollment through ongoing management:

```text
Plan
  |
  v
Configure Intune
  |
  v
Enroll Devices
  |
  v
Configure Windows
  |
  v
Apply Compliance
  |
  v
Integrate Conditional Access
  |
  v
Secure Endpoints
  |
  v
Deploy Applications
  |
  v
Manage Devices & Updates
  |
  v
Monitor & Operate
```

## Key Technologies

- Microsoft Intune
- Microsoft Entra ID
- Microsoft 365
- Microsoft Entra Conditional Access
- Windows 11
- Windows Autopilot
- Microsoft Defender
- BitLocker
- Microsoft Edge
- Microsoft 365 Apps
- VMware Workstation
- PowerShell
- Microsoft Graph

## Project Principles

The implementation is guided by the following principles:

- **Least privilege** — administrative access should use the appropriate role rather than unnecessary Global Administrator privileges.
- **Centralized management** — device configuration and security should be managed from Intune where practical.
- **Zero Trust** — access decisions should consider identity, device state, compliance, and security posture.
- **Policy-driven configuration** — settings should be defined through reusable Intune policies rather than manual device configuration.
- **Reproducibility** — significant configuration decisions and procedures should be documented.
- **Scalability** — the lab uses three devices but is structured so the design can be extended to a larger device fleet.

## Relationship to Project 1

This project is built on the Microsoft 365 foundation created in:

**Enterprise Microsoft 365 Deployment**

That project established the tenant and core services used by this lab, including Microsoft Entra ID, Microsoft 365 licensing, identity management, security controls, and Conditional Access.

Project 2 extends that foundation into endpoint management with Microsoft Intune.

```text
Project 1
Enterprise Microsoft 365 Deployment
                |
                v
      Identity & Security Foundation
                |
                v
Project 2
Enterprise Intune Device Management
                |
                v
       Managed & Secure Devices
```

## Expected Outcome

At the completion of this project, the three Windows 11 virtual devices should be centrally managed through Microsoft Intune with documented configuration for:

- Enrollment and device identity
- Configuration profiles
- Compliance
- Conditional Access integration
- Endpoint security
- Application deployment
- Windows update management
- Device administration
- Monitoring and troubleshooting


## Status

**Project:** In Progress  
**Environment:** Microsoft 365 + Microsoft Intune + VMware Workstation  
**Devices:** 4 Windows 11 virtual machines

---

Part of the **Project Zero — Enterprise Microsoft 365 & Cloud Infrastructure Lab**.
