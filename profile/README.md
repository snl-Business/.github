# Welcome to SNL Business 🚀

## About SNL Business

SNL Business is committed to building high-quality, maintainable software following industry-leading standards including NASA coding guidelines and SOLID principles.

## 📚 Our Repositories

### **Backend Services (Go)**
- **[Go-Excel-Processor](https://github.com/snl-Business/Go-Excel-Processor)** - Zero-dependency Excel file processor following NASA standards
- **[position-mapping-backend](https://github.com/snl-Business/position-mapping-backend)** - Position mapping service with Excel processing capabilities

### **Frontend Libraries (React/TypeScript)**
- **[UI-Component-Library](https://github.com/snl-Business/UI-Component-Library)** - Reusable React component library distributed via GitHub Packages NPM
- **[Auth-Blocks](https://github.com/snl-Business/Auth-Blocks)** - Authentication components and utilities

### **Standards & Documentation**
- **[coding-standards](https://github.com/snl-Business/coding-standards)** - Organization-wide coding standards and style guides
  - [C# Coding Standards and Style Guide](https://github.com/snl-Business/coding-standards/blob/main/c-sharp/C%23%20Standards%20and%20Style%20Guide.md)
- **[.github](https://github.com/snl-Business/.github)** - Organization defaults (Github standards, reviewers, branch naming, issues, and PR templates)

## 🎯 Development Standards

All SNL Business projects follow:

### **NASA Coding Standards**
- Single Responsibility Principle: ~70 lines per file/class
- Clear, descriptive naming conventions
- Comprehensive documentation
- Thorough testing requirements

### **SOLID Principles**
- **S**ingle Responsibility
- **O**pen/Closed
- **L**iskov Substitution
- **I**nterface Segregation
- **D**ependency Inversion

### **Code Review Requirements**
- All changes require pull requests
- Code owner approval required (via CODEOWNERS)
- Passing tests and CI/CD checks
- Conversation resolution before merge

## 📖 Resources

### **Coding Standards**
- [C# Standards and Style Guide](https://github.com/snl-Business/coding-standards/blob/main/c-sharp/C%23%20Standards%20and%20Style%20Guide.md)
- [Go Best Practices](https://github.com/snl-Business/Go-Excel-Processor) - See library implementation
- [React/TypeScript Guidelines](https://github.com/snl-Business/UI-Component-Library)

### **Templates & Workflows**
- [Pull Request Template](https://github.com/snl-Business/.github/blob/main/PULL_REQUEST_TEMPLATE.md)
- [Bug Report Template](https://github.com/snl-Business/.github/blob/main/ISSUE_TEMPLATE/bug_report.yml)
- [Feature Request Template](https://github.com/snl-Business/.github/blob/main/ISSUE_TEMPLATE/feature_request.yml)
- [Branch Protection Guide](https://github.com/snl-Business/.github/blob/main/BRANCH_PROTECTION.md)

### **Package Management**
- **Go Modules**: `go get github.com/snl-Business/<package>@version`
- **NPM Packages**: `npm install @snl-business/ui` (via GitHub Packages)

## 🚀 Quick Start

### **For New Team Members**

1. **Set Up GitHub Access**
   - Request organization access from your manager
   - Configure 2FA (two-factor authentication)
   - Generate Personal Access Token with `read:packages` and `write:packages`

2. **Configure Development Environment**
   
   **For Go Projects:**
   ```bash
   # Set private module access
   $env:GOPRIVATE = "github.com/snl-Business/*"
   
   # Install dependencies
   go mod download
   ```
   
   **For React/NPM Projects:**
   ```bash
   # Configure NPM for GitHub Packages
   npm config set @snl-business:registry https://npm.pkg.github.com
   npm config set //npm.pkg.github.com/:_authToken YOUR_GITHUB_TOKEN
   
   # Install dependencies
   npm install
   ```

3. **Review Coding Standards**
   - Read relevant language standards
   - Review example implementations
   - Set up linting tools

### **For New Projects**

1. **Choose Project Template**
   - Use organization templates when available
   - Follow repository naming conventions
   - Include proper README and documentation

2. **Apply Standards**
   - Add `.github/CODEOWNERS` (or use org default)
   - Set up CI/CD workflows
   - Enable branch protection
   - Add comprehensive tests

3. **Register with Team**
   - Add to appropriate GitHub team
   - Document in organization README
   - Share with relevant stakeholders

## 🛠️ Tools & Packages

### **Published Packages**

#### Go Modules
- `github.com/snl-Business/Go-Excel-Processor` - Excel file processing
  ```bash
  go get github.com/snl-Business/Go-Excel-Processor@v1.0.0
  ```

#### NPM Packages
- `@snl-business/ui` - React UI components
  ```bash
  npm install @snl-business/ui
  ```

### **Development Tools**

**Go Projects:**
- Go 1.21+ required
- Standard library preferred (minimal external dependencies)
- Testing: `go test ./...`
- Linting: `golangci-lint`

**React/TypeScript Projects:**
- Node.js 18+ required
- TypeScript strict mode
- Testing: Jest, React Testing Library
- Linting: ESLint + Prettier

## 👥 Teams & Ownership

### **GitHub Teams**
- `@snl-Business/engineering-leads` - Technical leadership and architecture
- `@snl-Business/backend-team` - Go and backend development
- `@snl-Business/frontend-team` - React and TypeScript development
- `@snl-Business/devops` - CI/CD and infrastructure
- `@snl-Business/security-team` - Security reviews
- `@snl-Business/database-admins` - Database schema and migrations

### **Responsibilities**
- **Engineering Leads**: Architecture decisions, standards enforcement, code review oversight
- **Backend Team**: Go services, APIs, data processing
- **Frontend Team**: React components, UI/UX, client-side logic
- **DevOps**: CI/CD, deployments, infrastructure, monitoring
- **Security Team**: Security reviews, vulnerability assessments
- **Database Admins**: Schema design, migrations, performance optimization

## 🔒 Security & Compliance

### **Security Practices**
- Two-factor authentication required
- Regular dependency updates
- Security scanning in CI/CD
- Code review for security-sensitive changes
- Access control via GitHub teams

### **Branch Protection**
- Direct pushes to `main` and `dev` blocked
- Pull request reviews required
- Status checks must pass
- CODEOWNERS approval enforced

### **Dependency Management**
- Regular security updates
- Minimal external dependencies
- Dependabot alerts enabled
- Vulnerability scanning in CI/CD

## 📊 CI/CD & Quality

### **Continuous Integration**
- Automated testing on all PRs
- Code coverage reporting
- Linting and formatting checks
- Security scanning

### **Quality Metrics**
- Code coverage targets (aim for 80%+)
- NASA standards compliance (70 lines per file)
- Zero critical security vulnerabilities
- All tests passing before merge

## 📞 Support & Contact

### **Getting Help**
- **Technical Questions**: Open an issue in the relevant repository
- **Access Issues**: Contact your manager or DevOps team
- **Standards Questions**: Review [coding-standards](https://github.com/snl-Business/coding-standards) or ask Engineering Leads
- **Security Concerns**: Contact Security Team immediately

### **Useful Links**
- [Organization Teams](https://github.com/orgs/snl-Business/teams)
- [Organization Settings](https://github.com/organizations/snl-Business/settings/profile)
- [Coding Standards Repository](https://github.com/snl-Business/coding-standards)
- [Internal Documentation](https://github.com/snl-Business/.github)

## 🎓 Learning Resources

### **External Resources**
- [NASA C Coding Standards](http://lars-lab.jpl.nasa.gov/JPL_Coding_Standard_C.pdf)
- [SOLID Principles](https://en.wikipedia.org/wiki/SOLID)
- [Go Best Practices](https://go.dev/doc/effective_go)
- [React Best Practices](https://react.dev/learn)

### **Internal Training**
- Review existing codebase for patterns
- Pair programming with senior developers
- Code review participation
- Documentation contributions

## 📝 Contributing

### **How to Contribute**

1. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes**
   - Follow coding standards
   - Add/update tests
   - Update documentation

3. **Submit a pull request**
   - Use PR template
   - Reference related issues
   - Request review from code owners

4. **Address feedback**
   - Respond to review comments
   - Make requested changes
   - Ensure CI/CD passes

### **Commit Message Format**
```
type: brief description

Detailed description if needed

- Bullet points for key changes
- Reference issues: Fixes #123
```

**Types**: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

## 📈 Roadmap

### **Current Initiatives**
- Expanding Go library ecosystem
- React component library enhancements
- CI/CD automation improvements
- Security scanning implementation

### **Upcoming**
- Additional coding standards (Python, JavaScript)
- Centralized logging and monitoring
- Enhanced testing frameworks
- Performance optimization guidelines

---

## 📄 License

Internal use only - SNL Business proprietary software.

## 🌟 Our Principles

1. **Quality Over Speed** - We build it right the first time
2. **Standards Compliance** - NASA coding standards and SOLID principles
3. **Team Collaboration** - Code review and pair programming
4. **Continuous Learning** - Always improving our craft
5. **Security First** - Security is everyone's responsibility

---

**Welcome to the team! Let's build something amazing together.** 🚀
