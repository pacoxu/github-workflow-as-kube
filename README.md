# github-workflow-as-kube

## Commands

This workflow following [Kubernetes habits](https://prow.k8s.io/command-help?repo=kubernetes%2Fkubernetes), offering commands:

| Name | Add | Remove | Note |
| ---- | ----- | ----- | -----|
| Good First Issue | /good-first-issue | /remove-good-first-issue | |
| Help | /help | /remove-help | |
| LGTM | /lgtm | /lgtm cancel | |
| Approve | /approve | /approve cancel | Only approvers have the privilege |
| Hold | /hold | /hold cancel | PR will not be merged once hold |
| Category | /kind _label_name_ | /remove-kind _label_name_ | |
| Assignment | /assign @_somebody_ | /unassign @_somebody_ | |

**NOTE**: PR will be auto-merged once have `lgtm` and `approved` labels and not under hold.

## How To Use

To use the workflow, you have to:

- Provide a `OWNERS` file, only the approvers have the privilege to tag `/approve` or `/approve cancel`
- Provide a github [secret](https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions) with the name of `AGENT_TOKEN`, it should have write privilege to your project.
- Add the `kube-actions.yaml` to your project under the path of `.github/workflows/`.
- Add additional labels to your project, like `approved`, `lgtm`, `do-not-merge/hold` and customized kind of labels.

## Roadmap

- Dispatch reviewers
- Test workflow support
