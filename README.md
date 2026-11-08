# Daniel Opara

### Identity and Access Management Engineer

**Okta | Microsoft Entra ID | Active Directory | Delinea PAM | PowerShell | Zero Trust**

![Okta](https://img.shields.io/badge/Okta-007DC1?style=for-the-badge&logo=okta&logoColor=white)
![Microsoft Entra ID](https://img.shields.io/badge/Microsoft%20Entra%20ID-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Active Directory](https://img.shields.io/badge/Active%20Directory-2F74C0?style=for-the-badge&logo=windows&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=for-the-badge&logo=powershell&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Zero Trust](https://img.shields.io/badge/Zero%20Trust-1F2937?style=for-the-badge&logo=securityscorecard&logoColor=white)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/nielopara)
[![Medium](https://img.shields.io/badge/Medium-Read-000000?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@dannyopara)
[![Email](https://img.shields.io/badge/Email-dannyopara%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:dannyopara@gmail.com)

---

## About

I design and run identity systems that decide who gets access to what, from where, and for how long. My day-to-day work covers joiner/mover/leaver automation, Conditional Access and MFA, SSO and SCIM integrations, privileged access, and access reviews that hold up in PCI DSS and NIST SP 800-53 audits.

This GitHub holds the labs and automation I build to practice and document that work in enterprise-style environments.

---

## Spotlight: DanotechInc Entra ID IAM Program

An end-to-end, enterprise-style IAM program on **Microsoft Entra ID** for DanotechInc, a fictional 200-person B2B SaaS company with offices in Atlanta, London, Mexico City, Accra, and Lagos. A SOC 2 readiness assessment found 11 identity findings, including a single Global Admin used daily, former staff keeping SaaS access for up to 11 months, access granted by copying colleagues, and long-lived secrets in CI/CD. The program fixes them phase by phase.

Every phase has its own folder with a scenario README, architecture diagrams, a walkthrough that explains *why* each step is done, scripts, and evidence. Every phase runs against a real 200-person HR dataset, including contractors, interns, pre-hires, and scheduled leavers, rather than a single test user.

**Delivered so far**

- **Governance (Phase 00):** program charter, RACI with named owners, naming conventions, architecture decision records, and a GitHub repo with branch protection and secret scanning with push protection.
- **Tenant foundation and hardening (Phase 01):** two FIDO2 break-glass accounts excluded from Conditional Access through a role-assignable group, Global Admin removed from the CEO's daily account, user consent and app registration locked down, security defaults replaced with three Conditional Access policies, a certificate-based read-only Graph automation app with no client secrets, Entra logs in Log Analytics, and a KQL alert on any break-glass sign-in.

**Design choices**

- HR is the only way accounts get created, with `employeeId` as the immutable join key.
- Access keys on job codes, not job titles.
- A 21-rule HR data quality gate includes a mass-change circuit breaker, so a truncated export can't disable 50 accounts.
- The RBAC model is data, simulated against all 200 people before building: 59 entitlements, 58 roles, 6 SoD rules, and 1 time-limited exception.
- Joiners never receive passwords; they get a one-time Temporary Access Pass to register a passkey.
- The build was re-sequenced around licence trial expiry, with an expiry-day runbook so the tenant is never left without MFA.

| Phase | Focus | Status |
| --- | --- | --- |
| 00 | Program charter and governance | Completed |
| 01 | Tenant foundation and hardening | Completed |
| 02 | Identity source and HR data model | In progress |
| 03 | RBAC design | In progress |
| 04 | Joiner/mover/leaver lifecycle automation | In progress |
| 05 | Groups, app roles, and an OIDC test app (Danotech Expenses) | In progress |
| 06 | Privileged access: admin accounts and PIM | Next |
| 07 | Authentication and Zero Trust Conditional Access: passkeys and risk | Planned |
| 08 | SSO and federation: SAML, OIDC, OAuth, SCIM across Salesforce, Atlassian, GitHub, Keycloak, Okta | Planned |
| 09 | Cloud IAM: Azure custom roles | Planned |
| 10 | Non-human identities: managed identities and workload identity federation | Planned |
| 11 | Agent-to-tool authorization for an AI agent with human approval | Planned |
| 12 | Entitlement management: access packages | Planned |
| 13 | Access reviews and audit readiness | Planned |
| 14 | Audit logging and monitoring: KQL, workbooks, Sentinel | Planned |
| 15 | Identity operations and risk analytics (ITDR) | Planned |
| 16 | Identity vulnerability management | Planned |
| 17 | Compliance mapping: SOC 2, ISO 27001, NIST CSF 2.0 | Planned |
| 18 | Capstone | Planned |

**Stack:** `Entra ID P2` `Entra Suite` `Microsoft Graph PowerShell` `Python` `Azure Log Analytics` `Azure App Service` `KQL` `GitHub Actions`

[View the repository](https://github.com/twitchy-fingers/danotechinc-entra-iam)

---

## Featured Projects

| Project | What It Shows | Stack |
| --- | --- | --- |
| [DanotechInc Entra IAM Program](https://github.com/twitchy-fingers/danotechinc-entra-iam) | 19-phase Entra ID program fixing 11 SOC 2 identity findings for a fictional 200-person company | `Entra ID` `Graph PowerShell` `Python` `KQL` |
| [AD Lifecycle Management Lab](https://github.com/twitchy-fingers/Active-Directory-Lifecycle-Management-Lab) | Joiner/mover/leaver automation and compliance-mapped access control | `Active Directory` `PowerShell` `RBAC` |
| [Continuous Authentication in a Zero Trust Environment](https://www.youtube.com/watch?v=oR90HkZEpWg) | GuidePoint Security capstone presentation implementing continuous authentication with Zscaler and Okta | `Okta` `Zscaler` `Zero Trust` |
| [Okta Org2Org Federation](https://medium.com/@dannyopara/okta-org2org-integration-using-aiw-46bb7a4b7192) | Hub-and-spoke SAML federation between US and EU Okta tenants for data sovereignty | `Okta` `Org2Org` `SAML 2.0` |
| [Okta and Salesforce SAML SSO](https://medium.com/@dannyopara) | SAML 2.0 single sign-on from Okta into Salesforce | `Okta` `Salesforce` `SAML 2.0` |
| [Okta Lab Environment](https://medium.com/@dannyopara) | Full Okta lab built and documented for the Okta Certified Professional exam | `Okta` `Lifecycle Management` |

---

## Writing

| Article | Published |
| --- | --- |
| [Okta Org2Org Integration Using AIW](https://medium.com/@dannyopara/okta-org2org-integration-using-aiw-46bb7a4b7192) | Jul 2025 |
| [Okta and Salesforce SAML SSO Integration](https://medium.com/@dannyopara) | Jun 2025 |
| [Everything Is Going To Be Ok-ta](https://medium.com/@dannyopara) | May 2025 |
| [Exam Prep: Microsoft Security Operations Analyst (SC-200)](https://medium.com/@dannyopara) | Aug 2023 |
| [Installing Splunk Enterprise on Ubuntu](https://medium.com/@dannyopara) | Jun 2023 |

---

## Experience Snapshot

| Role | Organization | Focus |
| --- | --- | --- |
| IT (IAM) Engineer | PCtronics Managed IT Services | JML automation, Entra Connect and SCIM, Conditional Access and MFA, PCI DSS access reviews |
| Cybersecurity Engineer (IAM/PAM) | GuidePoint Security | Delinea PAM with JIT access, SAML/OAuth/OIDC SSO, SCIM app onboarding, Okta Identity Threat Protection |
| IT Implementation Engineer | Acorn Technology Services | AD and Entra ID governance audits, PowerShell bulk automation, Entra Connect sync |
| Cybersecurity Assistant | Riverside City College | AD account lifecycle, access reviews, IAM training |

---

## Engineering Stack

| Domain | Technologies |
| --- | --- |
| Identity Platforms | Okta, Microsoft Entra ID, Active Directory, Entra Connect, Delinea Secret Server |
| Protocols | SAML 2.0, OIDC, OAuth 2.0, SCIM, LDAP |
| Access Models | RBAC, ABAC, Privileged Access Management, Just-in-Time Access, Zero Trust |
| Automation | PowerShell, Microsoft Graph, Python, KQL |
| Governance | Access Reviews, Entitlement Audits, PCI DSS, NIST SP 800-53 |

---

## Certifications

| Certification | Issuer |
| --- | --- |
| Certified Information Systems Security Professional (CISSP) | ISC2 |
| Okta Certified Administrator | Okta |
| Delinea Secret Server Associate | Delinea |
| Microsoft Certified: Security Operations Analyst (SC-200) | Microsoft |
| Splunk Core Certified Power User | Splunk |
| CompTIA Security+ | CompTIA |

---

## Roadmap

My roadmap is the DanotechInc program above. Upcoming phases cover PIM and privileged access, passkeys and risk-based Conditional Access, SSO and SCIM federation, non-human identities, access reviews, and SOC 2 / ISO 27001 compliance mapping.
