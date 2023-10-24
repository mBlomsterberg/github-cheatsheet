# Reusable Workflows

## Callee 
```yaml
name: Reusable Workflow

on: 
    workflow_call: 

jobs: 
    reusable_workflow_job:
        runs_on: ubuntu_latest
        steps: 
            - name: Greeting
               run: echo 'Hello from reusable workflow'
```

## Caller
```yaml
name: Consumer of Reusable Workflow

on: 
    push: 

jobs: 
    consumer_workflow_job:
        uses: mBlomsterberg/github-cheatsheet/.github/workflows/reusable-workflow.yml@main
```


<div>
    <br/>
    <br/>
</div>


## Callee with options
```yaml
name: Callee Reusable Workflow w/ options

on: 
    workflow_call: 
        inputs: 
            environment: 
                required: true
                type: string
            greeting: 
                required: false
                type: string
                default: 'Hello there!'
        secrets: 
            super_secret_endpoint: 
                required: true

jobs: 
    reusable_workflow_job:
        runs_on: ubuntu_latest
        environment: ${{inputs.environment}}
        steps: 
            - name: Greeting
               run: echo ${{inputs.greeting}}
            
            - name: Secret
               run: curl -f '${{ secrets.super_secret_endpoint }}/repos/'
```

## Caller with options
```yaml
name: Caller Reusable Workflow w/ options

on: 
    push: 

jobs: 
    consumer_workflow_job:
        uses: mBlomsterberg/github-cheatsheet/.github/workflows/reusable-workflow.yml@main
        with: 
            environment: prod
            greeting: 'Hello!'
        secrets: 
            super_secret_endpoint: ${{ secrets.repository_secret_endpoint }}
```