# SNL Business - Organization Defaults

This is a special repository that provides **default files and templates** for all repositories in the `snl-Business` organization.

## What This Repository Does

Files in this repository are automatically used by **all repositories** in the organization that don't have their own versions:

- ✅ `CODEOWNERS` - Default code review assignments
- ✅ `PULL_REQUEST_TEMPLATE.md` - Default PR template
- ✅ `ISSUE_TEMPLATE/` - Issue templates for bugs, features, etc.
- ✅ `workflow-templates/` - Reusable GitHub Actions workflows

## Structure

```
.github/
├── CODEOWNERS                      ← Applied to all repos by default
├── BRANCH_PROTECTION.md            ← Branch protection setup guide
├── PULL_REQUEST_TEMPLATE.md        ← Default PR template
├── ISSUE_TEMPLATE/
│   ├── bug_report.md
│   ├── feature_request.md
│   └── config.yml
└── workflow-templates/
    ├── go-ci.yml                   ← Go testing and building
    ├── go-ci.properties.json
    ├── react-ci.yml                ← React testing and building
    └── react-ci.properties.json
```

## How It Works

### For CODEOWNERS
1. GitHub checks each repository for `.github/CODEOWNERS`
2. If not found, it uses `snl-Business/.github/CODEOWNERS`
3. Individual repos can override by creating their own

### For PR Templates
1. When opening a PR, GitHub looks for the template
2. Uses org-level template if repo doesn't have one
3. Provides consistent PR descriptions across all repos

### For Workflow Templates
1. Appears in "Actions" tab → "New workflow" → "By snl-Business"
2. Team members can add pre-configured workflows
3. Ensures consistent CI/CD across projects

## Overriding Defaults

Individual repositories can override any default by creating their own version:

```bash
# In any repo
mkdir -p .github
cp path/to/custom/CODEOWNERS .github/CODEOWNERS
git add .github/CODEOWNERS
git commit -m "feat: add repository-specific CODEOWNERS"
```

## Maintenance

### Updating Organization Defaults
1. Make changes to this repository
2. Push to `main` branch
3. Changes apply immediately to all repos without their own versions

### Team Responsibilities
- **DevOps Team**: Maintains workflow templates
- **Engineering Leads**: Maintains CODEOWNERS
- **All Teams**: Can propose updates via PR

## Benefits

✅ **Consistency**: All repos follow same standards by default  
✅ **Less Duplication**: No need to copy files to every repo  
✅ **Easy Updates**: Change once, applies everywhere  
✅ **New Repos**: Automatically get best practices  
✅ **Flexibility**: Individual repos can still customize  

## Setup Instructions

### For Organization Owners:
1. This repository **must** be named exactly `.github`
2. Repository **must** be public (for open orgs) or internal
3. Located at: `https://github.com/snl-Business/.github`

### For Team Members:
- When creating new repos, these defaults apply automatically
- Check "Actions" tab for available workflow templates
- Review this repo for current standards

## Documentation

- [CODEOWNERS Documentation](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)
- [Organization Templates](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file)
- [Workflow Templates](https://docs.github.com/en/actions/using-workflows/creating-starter-workflows-for-your-organization)

## Support

For questions or suggestions:
- Open an issue in this repository
- Contact the DevOps team
- Review internal documentation wiki

---

**Note**: This is an organization-level repository. Changes here affect **all** SNL Business repositories.
