
# GitHub Workflow configuration


## Triggers
```yaml 
name: github cheatsheet

on: 
  branch_protection_rule:
    types: [created, edited, deleted]
  check_run:
    types: [created, rerequested, completed, requested_action]
  check_suite:
    types: [completed]
  create:
  delete:
  deployment:
  deployment_status:
  discussion:
    types: [created, edited, deleted, transferred, pinned, unpinned, labeled, unlabeled, locked, unlocked, category_changed, answered, unanswered]
  discussion_comment:
    types: [created, edited, deleted]
  fork:
  gollum:
  issue_comment:
    types: [created, edited, deleted]
  issues:
    types: [opened, edited, deleted, transferred, pinned, unpinned, closed, reopened, assigned, unassigned,
            labeled, unlabeled, locked, unlocked, milestoned, demilestoned]
  label:
    types: [created, edited, deleted]
  milestone:
    types: [ created, closed, opened, edited, deleted]
  page_build:
  project:
    types: [created, closed, reopened, edited, deleted]
  project_card:
    types: [created, moved, converted, edited, deleted]
  project_column:
    types: [created, updated, moved, deleted]
  public:
  pull_request:
    types: [assigned, unassigned, labeled, unlabeled, opened, edited, closed, reopened, synchronize, 
            converted_to_draft, ready_for_review, locked, unlocked, review_requested, review_request_removed, 
            auto_merge_enabled, auto_merge_disabled]
    branches:
      - 'default'
      - 'feature/*'
    paths:
      - '***.js'
  pull_request_comment:
  pull_request_review:
    types: [submitted, edited, dismissed]
  pull_request_review_comment:
    types: [created, edited, deleted]
  pull_request_target:
    types: [assigned, unassigned, labeled, unlabeled, opened, edited, closed, reopened, synchronize,
            converted_to_draft, ready_for_review, locked, unlocked, review_requested, review_request_removed,
            auto_merge_enabled, auto_merge_disabled]
    branches:
      - 'default'
      - 'feature/*'
    paths:
      - '***.js'
  push:
    branches:
      - 'default'
      - 'feature/*'
    branches-ignore:
      - 'default'
      - 'feature/*'
    paths:
      - '***.js'
    paths-ignore:
      - '***.js'
    tags:
      - 'v1.**'
    tags-ignore:
      - 'v1.**'
  registry_package:
    types: [published, updated]
  release:
    types: [published, unpublished, created, edited, deleted, prereleased, released]
  repository_dispatch:
    types: [something-you-choose]
  schedule:
              # ┌───────────── minute (0 - 59)
              # │  ┌───────────── hour (0 - 23)
              # │  │    ┌───────────── day of the month (1 - 31)
              # │  │    │   ┌───────────── month (1 - 12 or JAN-DEC)
              # │  │    │   │ ┌───────────── day of the week (0 - 6 or SUN-SAT)
              # │  │    │   │ │
              # │  │    │   │ │
              # │  │    │   │ │
              # *  *    *   * *
    - cron:    '30 5,17 5-7 * *'
      # (5:30 and 17:30 runs on the 5th to 7th every month)
      # https://crontab.guru/#5_*_*_*_*
  status:
  watch:
    types: [started]
  workflow_call:
  workflow_dispatch:
    inputs:
      logLevel:
        description: 'Log level'     
        required: true
        default: 'warning' 
        type: choice
        options:
        - info
        - warning
        - debug 
      tags:
        description: 'Test scenario tags'
        required: false 
        type: boolean
      environment:
        description: 'Environment to run tests against'
        required: true 
        type: environment

  workflow_run:
    workflows: [some_workflow]
    types: [completed, requested]
    branches: [develop]
```