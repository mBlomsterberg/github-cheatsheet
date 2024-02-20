<br />
<div id="readme-top" align="center">

  <h3 align="center">GitHub Workflows</h3>

  <p align="center">
    GitHub Workflow cheatsheet.
    <br />
    <br />
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/workflows/MATRIX.md">Matrix</a>
    ·
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/workflows/REUSABLE.md">Reusable</a>
  </p>
  <br />
</div>

<br>

# Workflows

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