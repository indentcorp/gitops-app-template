# GitOps Application Template

# Prerequisite
- Clone [GitOps Infrastructure Template](https://github.com/indentcorp/gitops-infra-template) and refer to the following `README.md` for customizing project.
- Install [`kubectl`](https://kubernetes.io/docs/tasks/tools/).
- Create ECR Repository for application.

# Workflow
![workflow](static/workflow.png)

# Customization
## `.github/workflows/ci.yml`
1. Register "Actions secrets" as below.
    - `ECR_REPOSITORY_NAME`: Amazon ECR Repository name.
    - `AWS_ACCESS_KEY_ID`: AWS IAM Access Key ID.
    - `AWS_SECRET_ACCESS_KEY`: AWS IAM Secret Access Key.
    - `GITHUB_PERSONAL_ACCESS_TOKEN`: Github personal access token. Select all of `repo` scope. Generate [here](https://github.com/settings/tokens)
1. Edit the name of infrastructure repository. (Line 60)
1. Edit the name of kustomize image name. (Line 84)
1. If you want to utilize `prod` stage, duplicate from line 82~85.

## `src/`
1. Source of your application should be here.
1. If you want to locate to other directory, `.github/workflows/ci.yml` should be changed. (Line 41)
