# Modernization Plan: SupplyChain Frontend on Azure

**Project**: SupplyChain Frontend

---

## Technical Framework

- **Language**: Java 8
- **Framework**: Spring Boot 2.7.18
- **Build Tool**: Maven; WAR packaging
- **Database**: None identified in the frontend
- **Key Dependencies**: Spring Web, embedded Tomcat, JSP/JSTL, Lombok
- **Application interface**: JSP-based web UI with backend REST API calls

---

## Overview

> This plan prepares the SupplyChain Frontend for Azure by placing the existing
> web application on Azure Container Apps. The app currently packages as a WAR
> and runs on a Java 8 Tomcat image. The modernization will:
>
> - Make the existing frontend available through an Azure-managed application
>   endpoint.
> - Preserve its current pages and backend API integration.
> - Verify the application and its container dependencies before deployment.
>
> No application framework upgrade, backend-service migration, or new Azure
> infrastructure provisioning was specified. The Azure Container Apps target
> and mock integration-test approach use questionnaire defaults.

---

## Migration Impact Summary

| App | Current | Azure | Auth | Notes |
|---|---|---|---|---|
| Frontend | Tomcat WAR | ACA | TBD | Existing UI |

---

## Open Questions & Questionnaire

- [x] Q: Should infrastructure be provisioned? → A: No; use the default of no
  new provisioning. An existing Azure Container Apps environment is required.
- [x] Q: Should integration testing be included? → A: Yes; use mocked
  dependencies because no Azure environment details were provided.
- [x] Q: Should security/CVE remediation be included? → A: Yes, the default.
- [x] Q: Which Azure deployment target? → A: Azure Container Apps, the default.
- [ ] Which existing Azure Container Apps environment and deployment
  configuration should be used?
- [ ] Should the documented Java/Spring Boot and ServiceMesh tech-debt items
  become explicit migration scope?

---

## Scope Notes

- No Java/Spring upgrade or application-service transform is included because
  neither was explicitly requested. The repository README documents potential
  technical-debt items for a future scope decision.
- Azure Container Apps is selected as the deployment default. Provisioning is
  excluded; deployment requires a separately available target environment.
- Containerization is covered by the deployment task; no separate
  containerization task is needed.
