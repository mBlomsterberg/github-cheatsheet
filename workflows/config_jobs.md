
# Potential Job Configuration

```yaml
################# JOBS 
env:                   ##  Global environment variable
  AWS_DEFAULT_REGION: ${{ secrets.AWS_REGION }} 
  ENV_VAR: ${{ vars.ENV_CONTEXT_VAR }}

permissions: read-all  ## workflow permission if nothing else is specified 

concurrency:
  group: ${{ github.workflow }} ## concurrency group. Can be anything
  cancel-in-progress: true ## cancel previous workflow run if new one is triggered

jobs:
  job_name_0:          ## Unique name for workflow job
      if: ${{ github.event.pull_request.merged }} ## Conditional run 
      name: 'name-of-job'    ## Workflow name
      environment:
        name: dev            ## specify which environment to run on 
        url: ${{steps.}}     ## Display a url after workflow run 
      runs-on: ubuntu-latest ## Operating system https://docs.github.com/en/actions/using-github-hosted-runners/about-github-hosted-runners/about-github-hosted-runners#supported-runners-and-hardware-resources
      container: cypress/browsers:node16.13.0-chrome95-ff94
      concurrency: 
        group: ${{github.ref}} ## concurrency group. Can be anything
        cancel-in-progress: true ## cancel previous workflow run if new one is triggered
      defaults: ## default settings
        run:
          shell:  bash         # Default shell
                  pwsh         # PowerShell Core
                  python       # Python command
                  sh           # fallback behavior for non-Windows platforms if no shell is provided
                  cmd          # GitHub appends the extension .cmd to your script name and substitutes for {0}.
                  powershell   # PowerShell Desktop
          working-directory: ./temp ## default working directory

      permissions: ## github.token permissions   https://docs.github.com/en/actions/using-jobs/assigning-permissions-to-jobs
        actions: read|write|none             ## Sets the GitHub Actions permissions policy for enabling GitHub Actions and allowed actions and reusable workflows in the repository.
        checks: read|write|none              ## Work with check runs and check suites. For example, checks: write permits an action to create a check run.
        contents: read|write|none            ## Work with the contents of the repository. For example, contents: read permits an action to list the commits, and contents:write allows the action to create a release. 
        deployments: read|write|none         ## Work with deployments. For example, deployments: write permits an action to create a new deployment.
        discussions: read|write|none         ## Work with GitHub Discussions. For example, discussions: write permits an action to close or delete a discussion.
        id-token: read|write|none            ## Fetch an OpenID Connect (OIDC) token. This requires id-token: write. 
        issues: read|write|none              ## Work with issues. For example, issues: write permits an action to add a comment to an issue.
        packages: read|write|none            ## Work with GitHub Packages. For example, packages: write permits an action to upload and publish packages on GitHub Packages.
        pages: read|write|none               ## Work with GitHub Pages. For example, pages: write permits an action to request a GitHub Pages build.
        pull-requests: read|write|none       ## Work with pull requests. For example, pull-requests: write permits an action to add a label to a pull request.
        repository-projects: read|write|none ## Work with GitHub projects (classic). For example, repository-projects: write permits an action to add a column to a project (classic).
        security-events: read|write|none     ## Work with GitHub code scanning and Dependabot alerts. For example, security-events: read permits an action to list the Dependabot alerts for the repository, and security-events: write allows an action to update the status of a code scanning alert.
        statuses: read|write|none            ## Work with commit statuses. For example, statuses:read permits an action to list the commit statuses for a given reference.

      needs: [build, deploy] ## dependency to other job(s) in same workflow
      env:                   ## job scoped environment variables
        AWS_DEFAULT_REGION: ${{ secrets.AWS_REGION }}
      outputs:               ## job scoped output 'test' from step id: step_id_1
        output: ${{ steps.url_id.outputs.name }}

      steps: 
        - name: Checking out repo       ## Custom step name
          uses: actions/checkout@master ## step using a Composite Action
          with:                         ## input for composite action
            token: ${{ secrets.PAT_TOKEN }} (provides Personal access token - used for branch protection)

      # # # # # # # step with single shell execution - Runs always
        - name: single shell
          if: always()
          id: url_id
          run: echo "name=$GITHUB_REF" >> $GITHUB_OUTPUT

      # # # # # # # step with multiple shell executions - Runs on failure only
        - name: multiple shell executions
          if: failure()
          shell: bash
          run: |
            echo "Hello folder..."
            mkdir .hello
            cd .hello
            echo "This is a file" > file.txt 

      # # # # # # # step with declared working directory - Runs on success only
        - name: Success
          if: success()
          working-directory: .hello
          run: |
            echo "Added more text" >> file.txt  
            cat file.txt


  on-success:  ## Job on successful workflow run
    runs-on: ubuntu-latest
    if: ${{ github.event.workflow_run.conclusion == 'success' }}
    steps:
     - run: echo 'The triggering workflow passed'

  on-failure: ## Job on failed workflow run
    runs-on: ubuntu-latest
    if: ${{ github.event.workflow_run.conclusion == 'failure' }}
    steps:
      - run: echo 'The triggering workflow failed'


```