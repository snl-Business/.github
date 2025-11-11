# Naming Standards

**Last Updated:** November 11, 2025

---

## GitHub Repository Names

**Format:** `PascalCase-With-Hyphens`

**Examples:**
- `Position-Mapping-Backend`
- `Auth-Blocks`
- `PMWeb-UI`

**Rules:**
- Use PascalCase for each word
- Separate words with hyphens (-)
- Be descriptive and concise

---

## Azure Container Registry (ACR) / Azure Container Apps (ACA) Image Names

**Format:** `lowercase-with-hyphens` (derived from GitHub repo name)

**Conversion Rule:**
- GitHub repo name → lowercase
- Keep hyphens

**Examples:**

| GitHub Repository | Azure Image Name |
|-------------------|------------------|
| `Position-Mapping-Backend` | `position-mapping-backend` |
| `Auth-Blocks` | `auth-blocks` |
| `PMWeb-UI` | `pmweb-ui` |

**Full Image Path:**
```
<registry>.azurecr.io/<image-name>:<tag>
```

Example:
```
snlacr.azurecr.io/position-mapping-backend:latest
```

---

## .NET Namespace & Project Structure

**Format:** Based on [Sargent Lundy naming patterns](https://teams.microsoft.com/l/message/19:d4e1c3a5b2f74e9a8c6d5e7f8a9b0c1d@thread.tacv2/1729795454000?tenantId=...)

**Namespace Hierarchy:**
```
SargentLundy.<Domain>.<Feature>.<Layer>
```

**Examples:**

```csharp
// Core library
SargentLundy.Core

// Specific domain - SPPQ (Supplier Pre-Qualification)
SargentLundy.SPPQ

// Service layer
SargentLundy.SPPQ.Services.Process

// Alternative structure
SargentLundy.Sppq.Services.Process
```

**Project File Names:**
- Match namespace exactly
- Use `.csproj` extension

**Examples:**
- `SargentLundy.Core.csproj`
- `SargentLundy.SPPQ.csproj`
- `SargentLundy.SPPQ.Services.Process.csproj`

**Folder Structure:**
```
src/
├── SargentLundy.Core/
│   ├── SargentLundy.Core.csproj
│   └── ...
├── SargentLundy.SPPQ/
│   ├── SargentLundy.SPPQ.csproj
│   └── ...
└── SargentLundy.SPPQ.Services.Process/
    ├── SargentLundy.SPPQ.Services.Process.csproj
    └── ...
```

**Rules:**
- Use PascalCase for all parts
- Acronyms for domain names (SPPQ)
- Follow layered architecture: Core → Domain → Services → Process/API

---

## Quick Reference

| Context | Format | Example |
|---------|--------|---------|
| **GitHub Repo** | `PascalCase-With-Hyphens` | `Position-Mapping-Backend` |
| **Azure Image** | `lowercase-with-hyphens` | `position-mapping-backend` |
| **.NET Namespace** | `SargentLundy.Domain.Layer` | `SargentLundy.SPPQ.Services.Process` |
| **.NET Project** | `{Namespace}.csproj` | `SargentLundy.SPPQ.Services.Process.csproj` |

---

## Examples by Project

### Position Mapping Backend

| Component | Name |
|-----------|------|
| GitHub Repo | `Position-Mapping-Backend` |
| Azure Image | `position-mapping-backend` |
| .NET Namespace | `SargentLundy.PositionMapping` |
| .NET Project | `SargentLundy.PositionMapping.API.csproj` |

### Auth Blocks

| Component | Name |
|-----------|------|
| GitHub Repo | `Auth-Blocks` |
| NPM Package | `@snl-business/auth-blocks` |
| React Component | `AuthBlocks` (PascalCase) |

### PMWeb UI

| Component | Name |
|-----------|------|
| GitHub Repo | `PMWeb-UI` |
| Azure Image | `pmweb-ui` |
| React App | `pmweb-ui` (package.json name) |

---

## Additional Standards

### File Names

**C# Files:**
- PascalCase: `EmployeeService.cs`, `IEmployeeRepository.cs`

**TypeScript/JavaScript:**
- camelCase for files: `employeeService.ts`
- PascalCase for components: `EmployeeCard.tsx`

**Configuration:**
- lowercase with dots: `appsettings.json`, `azure-pipelines.yml`

---

## References

- C# Coding Standards: `coding-standards/c-sharp/C# Standards and Style Guide.md`
- Azure Naming Conventions: [Microsoft Docs](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-naming)
