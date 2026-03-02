# GitHub Actions Lab - Thanh Tung Le

Repository: https://github.com/tungle2709/GitHubActionsLab-ThanhTungLe

## Workflows

### Workflow 1: dependent jobs (dependent-jobs.yml)

**Purpose:** Demonstrates job dependencies using the `needs` keyword.

**Trigger:** Push to main branch

**Execution Flow:**
1. `job_on_ubuntu` and `job_on_windows` run in parallel
2. `job_on_macos` runs after both complete
3. `Final_job` runs after macOS job completes

**Key Concepts:**
- `needs`: Creates job dependencies
- `runs-on`: Specifies runner OS
- Jobs without `needs` run in parallel

### Workflow 2: multi-platform (multi-platform.yml)

**Purpose:** Demonstrates parallel execution across multiple operating systems.

**Trigger:** Pull request to main branch

**Jobs:** Three independent jobs running simultaneously on Ubuntu, Windows, and macOS.

**Key Concepts:**
- No `needs` keyword means parallel execution
- `actions/checkout@v4`: Checks out code
- OS-specific commands

## Challenges

**Challenge:** Understanding job dependencies vs parallel execution  
**Solution:** Using `needs` creates dependencies; omitting it allows parallel execution.
