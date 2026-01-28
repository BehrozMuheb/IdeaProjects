# IdeaProjects

## Issue Processing Workflow

This repository uses GitHub Actions to automate issue-branch association and PR management for streamlined development.

### Workflow Overview

- **Issue Opened**: Automatically creates a feature branch in the format `feature/<issue-number>-<slug>` and updates the issue body with branch and status information.
- **Push to Feature Branch**: Posts a comment on the linked issue indicating commits have been pushed.
- **PR Opened from Feature Branch**: Links the PR to the issue via a comment and automatically adds `Fixes #<issue-number>` to the PR description if missing.
- **PR Guard**: Ensures all PRs reference an issue. For feature branches, the keyword is auto-added; for others, the PR is blocked if missing.

### Usage

1. Open a GitHub issue to initiate work on a feature.
2. A corresponding branch is created automatically.
3. Make commits and push to the branch to see status updates in the issue.
4. Open a pull request from the feature branch; closing keywords are added automatically.
5. Merge the PR to automatically close the issue.

### Acceptance Criteria

- Issues are associated with branches upon opening.
- Issue views display branch name and statuses (created, commits, PR).
- PR descriptions include `Fixes #<issue>` automatically for feature branches.
- PRs without issue references are warned/blocked.