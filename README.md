# GitHub Actions Lab - Thanh Tung Le

Repository: https://github.com/tungle2709/GitHubActionsLab-ThanhTungLe

## Testing Multi-Platform Workflow

This branch is for testing the multi-platform workflow with pull requests.

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

## Key Concepts Demonstrated

### needs
Creates dependencies between jobs. When a job specifies `needs: [other-job]`, it will only run after the specified job completes successfully. This ensures sequential execution.

### runs-on
Specifies the type of runner (virtual machine) that executes the job. Options include:
- `ubuntu-latest` - Linux environment
- `windows-latest` - Windows environment
- `macos-latest` - macOS environment

### env
Defines environment variables at workflow, job, or step level. Can be used to configure settings and pass values between steps (not used in these workflows but available for configuration).

## Challenges

**Challenge:** Understanding job dependencies vs parallel execution  
**Solution:** Using `needs` creates dependencies; omitting it allows parallel execution.

**Challenge:** OS-specific commands in multi-platform workflow  
**Solution:** Used appropriate commands for each OS (uname for Unix-like systems, systeminfo for Windows).
