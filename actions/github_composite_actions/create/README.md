<br />
<div id="readme-top" align="center">

  <h3 align="center">GitHub Composite Action Creation</h3>

  <p align="center">
    GitHub Actions
    <br />
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/actions/recommendations.md">Recommendations</a>
    ·
    <a href="https://github.com/mBlomsterberg/github-cheatsheet/blob/main/actions/orchestration.md">Orchestration</a>
  </p>
</div>

<br>

# Composite Action Creation



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