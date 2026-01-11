# Glossary

Comprehensive definitions of terms used in the Prompt Orchestration Governance (POG) framework.

---

## Core Concepts

### Prompt Orchestration Governance (POG)
A comprehensive framework for managing prompts as first-class software assets across the Software Development Life Cycle. POG provides systematic processes for discovering, normalizing, validating, versioning, and deploying prompts while maintaining governance and quality controls.

### Prompt
A structured, versioned artifact that encodes intent, constraints, and context for model-driven execution. In POG, prompts are treated as first-class software assets that are discoverable, testable, and reusable across projects and teams.

### First-Class Software Asset
A software artifact that receives the same level of rigor, management, and governance as source code. This includes version control, testing, documentation, review processes, and lifecycle management.

---

## Prompt Types

### Interaction Prompt
An ad-hoc, informal prompt used during exploration, chat interactions, or experimental work. These prompts are typically not governed and exist only in chat histories or personal notes.

**Example**: A one-off question asked in ChatGPT or Claude to solve an immediate problem.

**Lifecycle Stage**: Initial, ungoverned state.

### Discovered Prompt
An interaction prompt that has been identified as valuable and worth capturing for reuse. Discovery happens when a prompt demonstrates effectiveness and potential value beyond its original context.

**Example**: A code review prompt that consistently produces high-quality feedback, identified during a retrospective.

**Lifecycle Stage**: Nominated for promotion to governed asset.

### Normalized Prompt
A discovered prompt that has been transformed into a structured, parameterized, and generalized template. Normalization removes project-specific details and adds clear parameters.

**Example**:
```
Before: "Review this Python function for our auth service"
After: "Review the following {{LANGUAGE}} code for {{PURPOSE}}:\n{{CODE}}"
```

**Lifecycle Stage**: Structured but not yet validated.

### Validated Prompt
A normalized prompt that has passed testing against evaluation cases. Validation ensures the prompt produces consistent, high-quality results across different inputs.

**Example**: A test case generator that has been validated against 20 different function types and consistently produces comprehensive test suites.

**Lifecycle Stage**: Quality-assured and ready for production.

### Skill Prompt
A validated, production-ready, versioned, and governed prompt artifact. Skill prompts are the end goal of the POG lifecycle—reusable assets managed as part of organizational knowledge.

**Example**: "Code Review Assistant v2.1" stored in the prompt repository with full metadata, versioning, and usage tracking.

**Lifecycle Stage**: Production-ready, governed asset.

---

## POG Components

### Prompt Warehouse Management
The first core function of POG. A systematic process to discover, normalize, validate, version, and store prompts as reusable assets. Acts as a "factory" that transforms interaction prompts into skill prompts.

**Key Activities**:
- Discovery of valuable prompts
- Normalization into templates
- Validation against test cases
- Version control and storage

### SDLC Integration
The second core function of POG. Organization and deployment of phase-specific prompts to accelerate each stage of the Software Development Life Cycle.

**Key Activities**:
- Organizing prompts by SDLC phase
- Providing phase-appropriate prompts on demand
- Collecting usage feedback
- Continuous improvement

### Prompt Repository
A centralized, versioned store of governed prompt artifacts. The repository serves as the single source of truth for all skill prompts in an organization.

**Characteristics**:
- Version-controlled (typically Git-based)
- Searchable and discoverable
- Includes metadata (tags, usage stats, ratings)
- Access-controlled with governance

### Meta-Loop
The continuous improvement mechanism for the POG framework itself. The meta-loop collects usage data, feedback, and metrics to systematically improve the prompt library over time.

**Process**:
1. Teams use prompts from repository
2. Usage metrics and feedback collected
3. Performance evaluated
4. High-value prompts promoted
5. Low-value prompts deprecated
6. Gaps identified and filled

---

## Lifecycle Stages

### Discovery Phase
The process of identifying valuable interaction prompts worth capturing and formalizing. Discovery can be proactive (mining chat histories) or reactive (developers submitting prompts).

**Activities**:
- Mining chat histories and logs
- Developer submissions
- Team retrospectives
- Usage pattern analysis

### Normalization Phase
Transformation of discovered prompts into structured, parameterized templates that can be reused across contexts. Removes project-specific details and adds clear parameters.

**Activities**:
- Extract core intent
- Identify parameters
- Generalize constraints
- Add metadata
- Document usage

### Validation Phase
Testing prompts against evaluation cases to ensure quality, consistency, and effectiveness. Validation prevents poor-quality prompts from entering the repository.

**Activities**:
- Define test cases
- Execute against multiple inputs
- Measure quality metrics
- Gather peer review
- Approve or reject

### Repository Management
Ongoing maintenance of the prompt repository including versioning, organization, search, access control, and deprecation.

**Activities**:
- Version control
- Metadata management
- Search and discovery
- Access permissions
- Usage tracking
- Deprecation of outdated prompts

---

## SDLC Phases

### Requirements Phase
The initial stage of software development focused on understanding and documenting what needs to be built.

**POG Prompts**: User story generation, acceptance criteria, stakeholder interview guides, requirements validation.

### Design Phase
The stage focused on planning the architecture, interfaces, and data models for the system.

**POG Prompts**: Architecture pattern advice, API design, data model generation, design review.

### Development Phase
The stage focused on writing, reviewing, and documenting code.

**POG Prompts**: Code generation, code review, documentation generation, refactoring suggestions.

### Testing Phase
The stage focused on verifying the system works correctly and meets requirements.

**POG Prompts**: Test case generation, test data creation, bug analysis, coverage analysis.

### Deployment Phase
The stage focused on releasing the system to production environments.

**POG Prompts**: Release notes generation, configuration validation, deployment planning, rollback procedures.

### Maintenance Phase
The ongoing stage focused on monitoring, debugging, and improving the system in production.

**POG Prompts**: Incident analysis, performance optimization, technical debt assessment, documentation updates.

---

## Orchestration Concepts

### Orchestration Layers
A hierarchical organization of prompts by scope and abstraction level. Layers compose from bottom (foundation) to top (runtime context).

**Layers** (bottom to top):
1. **Foundation Layer**: Core capabilities and constraints
2. **Domain Layer**: Business rules and domain knowledge
3. **Task Layer**: Specific intents and actions
4. **Runtime Context Layer**: Dynamic user input and environment

### Foundation Layer
The base layer containing core system capabilities, safety constraints, and organizational policies that apply universally across all prompts.

**Examples**: Rate limits, content policies, security constraints, base model capabilities.

### Domain Layer
Business-specific rules, terminology, and patterns relevant to particular domains or industries.

**Examples**: Financial regulations, healthcare protocols, e-commerce patterns, legal terminology.

### Task Layer
Specific intents and actions that accomplish particular development tasks.

**Examples**: "Generate unit tests", "Review API design", "Create user story", "Analyze security vulnerabilities".

### Runtime Context Layer
Dynamic context including user input, project state, environment variables, and session information injected at execution time.

**Examples**: Current file content, user role, project language, git branch, environment (dev/staging/prod).

---

## Governance Concepts

### Control Plane
The governance mechanisms that manage prompt lifecycle including versioning, access control, audit trails, quality gates, and compliance.

**Components**:
- Versioning system
- Access control (RBAC)
- Audit logging
- Quality gates
- Compliance checks

### Version Control
Systematic tracking of changes to prompts over time. Each version has a unique identifier, change log, and maintains backward compatibility where possible.

**Approaches**:
- Git-based (tags, branches)
- Semantic versioning (v1.2.3)
- Timestamp-based
- Hash-based

### Access Control
Role-based permissions determining who can create, modify, approve, or use prompts.

**Common Roles**:
- **Contributor**: Can submit prompts
- **Reviewer**: Can approve/reject prompts
- **Maintainer**: Can manage repository
- **User**: Can consume prompts
- **Admin**: Full administrative access

### Audit Trail
Complete history of prompt usage including who used which prompt, when, for what purpose, and with what results.

**Tracked Information**:
- User identity
- Timestamp
- Prompt version
- Input/output (sanitized)
- Success/failure
- Feedback

### Quality Gate
A checkpoint in the prompt lifecycle requiring validation before progression. Quality gates ensure only tested, approved prompts reach production.

**Types**:
- Syntax validation
- Evaluation test passage
- Peer review approval
- Security scan
- Compliance check

---

## Evaluation & Testing

### Evaluation Case
A test case for a prompt consisting of an input scenario and expected output characteristics. Used to validate prompt quality and consistency.

**Components**:
- Input example
- Expected output pattern
- Quality criteria
- Pass/fail threshold

**Example**:
```
Input: "Review this code: function add(a,b) { return a+b }"
Expected: Contains "no error handling", "missing type hints"
Quality: Identifies at least 2 code quality issues
```

### Regression Test
A test ensuring a prompt continues to perform well after modifications. Prevents quality degradation during prompt evolution.

### A/B Test
Controlled comparison of two prompt variations to determine which performs better. Used for prompt optimization.

**Metrics**: Success rate, quality score, user preference, latency, cost.

### Usage Metrics
Quantitative data about prompt usage patterns including frequency, success rate, user ratings, and performance metrics.

**Collected Data**:
- Usage count
- Unique users
- Success/failure rate
- Average latency
- Cost per execution
- User satisfaction scores

---

## Implementation Approaches

### GitOps-Based
An implementation approach where prompts are stored as code in Git repositories with PR-based review workflows.

**Characteristics**:
- Prompts as markdown/YAML files
- Git for version control
- Pull requests for review
- CI/CD for validation
- Branch-based workflows

### Platform-Based
An implementation approach using dedicated prompt management platforms with UI-driven workflows.

**Characteristics**:
- Web-based interface
- Database-backed storage
- Built-in search and analytics
- Role-based access control
- API for programmatic access

### API-Driven
An implementation approach exposing RESTful APIs for programmatic prompt access and management.

**Characteristics**:
- REST/GraphQL APIs
- Programmatic access
- Integration-friendly
- Automation support
- Headless architecture

### Hybrid
A combination of approaches using multiple implementation strategies based on organizational needs.

**Example**: Git for version control + database for metadata + API for runtime access.

---

## Related Methodologies

### PDD (Prompt-Driven Development)
A development methodology where prompts are the primary drivers of the development process. Focuses on individual developer workflow and rapid iteration.

**Relationship to POG**: Complementary. PDD for development practices, POG for governance.

See: [POG vs PDD](comparisons/pdd.md)

### PDE (Prompt-Driven Engineering)
An engineering methodology treating prompts as first-class engineering artifacts requiring rigorous design, testing, and maintenance.

**Relationship to POG**: Complementary. PDE for engineering quality, POG for organizational management.

See: [POG vs PDE](comparisons/pde.md)

### PromptOps
Operational practices for managing prompt deployment, monitoring, and maintenance in production environments.

**Relationship to POG**: POG provides the governance framework; PromptOps provides operational practices.

### LLMOps
MLOps practices applied to Large Language Model lifecycle including model deployment, monitoring, and management.

**Relationship to POG**: POG focuses on prompts; LLMOps focuses on models. Both are complementary parts of AI operations.

---

## Technical Terms

### Parameterization
The process of identifying and extracting variable parts of a prompt into named parameters that can be filled at runtime.

**Example**:
```
Before: "Write Python tests for the authenticate function"
After: "Write {{LANGUAGE}} tests for the {{FUNCTION_NAME}} function"
```

### Context Injection
The process of automatically inserting relevant information into a prompt at runtime based on current project state, user session, or environment.

**Examples**:
- Current file content
- Git branch name
- Project dependencies
- User preferences
- Environment variables

### Template
A reusable prompt structure with parameters that can be filled with specific values. Templates enable prompt reuse across different contexts.

**Format Examples**:
- Jinja2: `{{ variable }}`
- Handlebars: `{{variable}}`
- Mustache: `{{variable}}`
- Custom: `$VARIABLE` or `{variable}`

### Metadata
Structured information about a prompt including tags, author, version, usage stats, ratings, and relationships.

**Common Fields**:
- Name and description
- Version and author
- Created/modified dates
- SDLC phase
- Tags and categories
- Usage statistics
- Quality ratings
- Related prompts

### Semantic Search
Search capability that understands meaning and intent rather than just matching keywords. Enables finding relevant prompts even with different wording.

**Technologies**: Vector embeddings, similarity search, semantic indexing.

---

## Metrics & Measurement

### Adoption Rate
Percentage of developers or teams actively using prompts from the POG repository.

**Calculation**: (Active users / Total users) × 100

### Reuse Rate
Frequency at which prompts are reused rather than created from scratch.

**Calculation**: (Prompts reused / Total prompt usage) × 100

### Time-to-Value
Duration from prompt discovery to production deployment in the repository.

**Target**: Minimize while maintaining quality.

### Coverage
Percentage of SDLC phases or development tasks that have available prompts.

**Calculation**: (Phases with prompts / Total phases) × 100

### Quality Score
Aggregated measure of prompt effectiveness based on validation tests, user ratings, and success metrics.

**Components**: Test pass rate, user satisfaction, success rate, peer reviews.

### ROI (Return on Investment)
Financial benefit gained from POG implementation compared to costs.

**Calculation**: (Time saved × Hourly rate - Operating costs) / Operating costs × 100

---

## Organizational Terms

### Prompt Champion
An enthusiastic advocate who promotes POG adoption, provides training, and supports users within a team or department.

**Responsibilities**: Evangelism, training, support, feedback collection.

### Prompt Maintainer
Person or team responsible for managing the prompt repository, reviewing submissions, and ensuring quality standards.

**Responsibilities**: Repository management, review/approval, quality assurance, deprecation decisions.

### Contributor
Any team member who creates and submits prompts to the repository.

**Responsibilities**: Create quality prompts, provide documentation, respond to feedback.

### Governance Team
Group responsible for establishing policies, standards, and compliance requirements for prompt management.

**Responsibilities**: Policy setting, compliance monitoring, audit reviews, risk management.

---

## Change Management

### Pilot Team
A small group selected to test POG implementation before organization-wide rollout. Provides feedback and identifies issues.

**Selection Criteria**: Enthusiastic, representative of broader organization, willing to provide feedback.

### Champions Network
A distributed group of prompt advocates across different teams who promote adoption and provide peer support.

### Quick Win
An early, visible success that demonstrates POG value and builds momentum for broader adoption.

**Examples**: 50% time savings on common task, faster onboarding, improved code quality.

---

*For complete framework documentation, see [Main POG Documentation](index.md).*
