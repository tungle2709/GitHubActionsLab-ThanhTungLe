# GitHub Actions Lab - Thanh Tung Le

Repository: https://github.com/tungle2709/GitHubActionsLab-ThanhTungLe

## Workflows

### Workflow 1: dependent jobs (dependent-jobs.yml)

**Purpose:** Demonstrates job dependencies using the `needs` keyword.

**Trigger:** Push to main branch

**Execution Flow:**
1. `build` job runs first
2. `test` job runs after build completes
3. `deploy` job runs after test completes

**Key Concepts:**
- `needs`: Creates job dependencies
- `runs-on`: Specifies runner OS
- Sequential execution: build → test → deploy

### Workflow 2: multi-platform (multi-platform.yml)

**Purpose:** Demonstrates parallel execution across multiple operating systems.

**Trigger:** Pull request to main branch

**Jobs:** Three independent jobs running simultaneously on Ubuntu, Windows, and macOS.

**Key Concepts:**
- No `needs` keyword means parallel execution
- `actions/checkout@v4`: Checks out code
- OS-specific commands

### Workflow 3: Java CI with Maven (maven.yml)

**Purpose:** Builds Java project with Maven.

**Trigger:** Push and pull requests to main branch

**Key Concepts:**
- Maven build automation
- JDK 17 setup
- Dependency caching

## Challenges

**Challenge:** Understanding job dependencies vs parallel execution  
**Solution:** Using `needs` creates dependencies; omitting it allows parallel execution.
