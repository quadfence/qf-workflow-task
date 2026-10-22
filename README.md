# qf-workflow-task

Task plumbing for Quadfence client workflows: `.github/workflows/task.yml` (reusable workflow) and `actions/wf-task`
(composite action). **Mirrored from the private hub repo by `tools/publish-plumbing.sh`; do not edit here.**

Call from a client repo:

```yaml
jobs:
  deploy:
    uses: quadfence/qf-workflow-task/.github/workflows/task.yml@v1
    with: { ... }   # see the example wrapper in the hub repo (.github/workflows/example-client-module-release.yml)
```

Contains no secrets and grants nothing: identity comes from the caller's own repo variables (WIF provider + runner SA)
and the hub only accepts events whose tenant, task_key and dispatch_token match a dispatch it made.

Source commit: f36e229 · tag v1.0.3
