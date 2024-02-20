<br />
<div id="readme-top" align="center">

  <h3 align="center">GitHub Workflows cheatsheet</h3>

  <p align="center">
    GitHub Workflow Config
    <br />
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/workflows/config.md">Configuration</a>
    ·
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/workflows/variables.md">Variables</a>
  </p>
  <p align="center">
    GitHub Example Workflows
    <br />
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/workflows/matrix.md">Matrix</a>
    ·
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/workflows/reusable.md">Reusable</a>
  </p>
</div>

<br>

# Workflows
>A workflow is a configurable automated process that will run one or more jobs. Workflows are defined by a YAML file checked in to your repository and will run when triggered by an event in your repository, or they can be triggered manually, or at a defined schedule. 
Workflows are defined in the .github/workflows directory in a repository, and a repository can have multiple workflows, each of which can perform a different set of tasks.

> Taken from https://docs.github.com/en/actions/using-workflows/about-workflows

Basic Workflow: 
```yaml
Name: Required Workflow name

on: 
  push: 
    branch: branch-name

jobs:
  job_name: must be unique
    runs-on: ubuntu-latest 

    steps:
    - uses: actions/checkout@v4

    - run: echo "hello world"

    - name: optional name for step
      run: echo "hello world"

    - name: optional name for step
      id: unique-id
      run: curl -X GET www.google.com
```