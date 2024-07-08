<br />
<div id="readme-top" align="center">

  <h3 align="center">GitHub Actions Cheatsheet</h3>

  <p align="center">
    GitHub Actions
    <br />
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/actions/github_actions/recommendation/recommendations.md">Recommendations</a>
    ·
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/actions/github_actions/orchestration/orchestration.md">Orchestration</a>
    ·
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/actions/github_actions/integration/integration.md">GitHub Integration</a>
  </p>
  <p align="center">
    GitHub Composite Actions
    <br />
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/actions/github_composite_actions/create/create.md">Create</a>
    ·
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/actions/github_composite_actions/reusable/reusable.md">Reusable</a>
  </p>
</div>

<br>

# Actions 



## Inputs

| Name                | Description                                                      | Type     | Default             | Required |
|---------------------|------------------------------------------------------------------|----------|---------------------|----------|
| `cluster`           | Name of the targeted ECS Cluster                                 | `string` | -                   | yes      |
| `service`           | Name of the targeted ECS service                                 | `string` | -                   | yes      |
| `aws-region`        | The AWS region we are working with                               | `string` | -                   | yes      |
| `aws-account-id`    | The AWS account ID                                               | `string` | -                   | yes      |


## Example of Action usage

```yml

      - name: Run Chaos Experiment
        uses: random/github-actions/kill-service-action@main
        with:
          cluster: foo-cluster
          service: bar-service
          aws-region: ${{ secrets.AWS_REGION }}
          aws-account-id: ${{ secrets.AWS_ACCOUNT_ID }}

```