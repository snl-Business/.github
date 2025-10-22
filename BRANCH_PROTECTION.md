# Branch Protection Setup Guide

## Overview
This guide explains how to set up CODEOWNERS and branch protection rules for all SNL Business repositories.

## Step 1: CODEOWNERS File Setup

The `CODEOWNERS` file has been added to `.github/CODEOWNERS`. This file automatically requests reviews from designated team members.

### Required GitHub Teams

Create these teams in your GitHub organization:
- `@snl-Business/engineering-leads` - Technical leads with full approval rights
- `@snl-Business/backend-team` - Go/backend developers
- `@snl-Business/frontend-team` - React/TypeScript developers
- `@snl-Business/devops` - DevOps and CI/CD specialists
- `@snl-Business/security-team` - Security reviewers
- `@snl-Business/database-admins` - Database administrators
- `@snl-Business/engineering-team` - All engineers

### How to Create Teams:
1. Go to: https://github.com/orgs/snl-Business/teams
2. Click "New team"
3. Add team members with appropriate permissions

## Step 2: Enable Branch Protection

### For Each Repository:

1. **Navigate to Repository Settings**
   - Go to: `https://github.com/snl-Business/<REPO_NAME>/settings/branches`

2. **Add Branch Protection Rule for `main`**
   - Click "Add branch protection rule"
   - Branch name pattern: `main`
   - Configure the following settings:

#### Required Settings:

✅ **Require a pull request before merging**
   - Require approvals: `1` (or more for critical repos)
   - Dismiss stale pull request approvals when new commits are pushed
   - Require review from Code Owners

✅ **Require status checks to pass before merging**
   - Require branches to be up to date before merging
   - Add status checks: (if using GitHub Actions)
     - `test` (go test)
     - `build` (go build)
     - `lint` (golangci-lint)

✅ **Require conversation resolution before merging**

✅ **Require signed commits** (optional but recommended)

✅ **Require linear history** (prevents merge commits)

✅ **Do not allow bypassing the above settings**
   - This prevents even admins from bypassing (recommended)

✅ **Restrict who can push to matching branches**
   - Select: `@snl-Business/engineering-leads`

3. **Add Branch Protection Rule for `dev`**
   - Repeat the same process for branch: `dev`
   - Can have slightly relaxed rules (e.g., fewer required approvals)

## Step 3: Repository Settings

### General Settings:
- ✅ Disable: "Allow merge commits" (use squash or rebase)
- ✅ Enable: "Automatically delete head branches"
- ✅ Enable: "Allow squash merging"
- ✅ Disable: "Allow rebase merging" (optional)

### Branch Settings:
- Default branch: `main` or `dev` (your choice)

## Step 4: Apply to All Repositories

Copy the CODEOWNERS file to each repository:

```bash
# For Go-Excel-Processor (already done)
cd go-excel-processor
git add .github/CODEOWNERS
git commit -m "chore: add CODEOWNERS for branch protection"
git push origin main

# For position-mapping-backend
cd ../position-mapping-backend
mkdir -p .github
cp ../go-excel-processor/.github/CODEOWNERS .github/
git add .github/CODEOWNERS
git commit -m "chore: add CODEOWNERS for branch protection"
git push origin main

# For UI-Component-Library
cd ../UI-component-Library
mkdir -p .github
cp ../go-excel-processor/.github/CODEOWNERS .github/
git add .github/CODEOWNERS
git commit -m "chore: add CODEOWNERS for branch protection"
git push origin main
```

## Step 5: Enable Organization-Wide Settings

### At Organization Level:
1. Go to: https://github.com/organizations/snl-Business/settings/member_privileges
2. **Base permissions**: Set to `Read` (not Write)
3. **Repository creation**: Restrict to organization owners
4. **Repository forking**: Disable for private repositories

### Security Settings:
1. Go to: https://github.com/organizations/snl-Business/settings/security
2. Enable: "Require two-factor authentication"
3. Enable: "Dependency graph"
4. Enable: "Dependabot alerts"
5. Enable: "Dependabot security updates"

## Step 6: Verify Setup

### Test the Protection:
1. Create a test branch
2. Make a change
3. Open a pull request to `main`
4. Verify:
   - ✅ CODEOWNERS are automatically requested as reviewers
   - ✅ Cannot merge without approval
   - ✅ Status checks must pass
   - ✅ Direct push to `main` is blocked

## Quick Setup Script

Run this PowerShell script to apply CODEOWNERS to all repos:

```powershell
$repos = @(
    "go-excel-processor",
    "position-mapping-backend", 
    "UI-component-Library",
    "Auth-Blocks"
)

foreach ($repo in $repos) {
    cd "C:\Users\0AB292\Coding\$repo"
    
    # Create .github directory if it doesn't exist
    if (!(Test-Path .github)) {
        New-Item -ItemType Directory -Path .github
    }
    
    # Copy CODEOWNERS
    Copy-Item "C:\Users\0AB292\Coding\go-excel-processor\.github\CODEOWNERS" ".github\" -Force
    
    # Commit and push
    git add .github/CODEOWNERS
    git commit -m "chore: add CODEOWNERS for branch protection"
    git push origin main
    
    Write-Host "✅ Applied CODEOWNERS to $repo" -ForegroundColor Green
}
```

## Maintenance

### Update CODEOWNERS when:
- Team structure changes
- New critical files/directories are added
- Ownership responsibilities shift

### Review Protection Rules:
- Quarterly review of team memberships
- Update required reviewers as team grows
- Adjust approval requirements based on team size

## Documentation

Keep this guide updated in each repository:
- Link in main README.md
- Store in `.github/BRANCH_PROTECTION.md`
- Include in onboarding documentation

## Support

For questions or issues:
- Contact: DevOps team
- Documentation: Internal wiki
- GitHub Support: https://support.github.com
