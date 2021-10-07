# Custom actions

Demo repository for using custom actions in a workflow.

This demo uses a mix of public and private actions to create a repository in the organization from a new issue. For the private actions, a GitHub App token is used to authenticate since the `GITHUB_TOKEN` is scoped to the workflow repo only.

## Usage 

### Create a new issue

1. In the repository, go to **Issues** and create a new issue based on the template
1. Update the `name` and `description` fields
    - :exclamation: The issue body must be `yml` compliant, do not change the indentation 
1. Click **Submit new issue**, this should trigger the workflow

### Observe the workflow

1. The new issue should have triggered the workflow
1. After the workflow is complete, there should be several updates:
    - The issue should have a few comments in it
    - In the organization, there should be a new (internal) repository created
1. Walk through the workflow and explain how the workflow is built
    - Public action used to retrieve the GitHub App authentication token used for checking out private actions
    - Private actions checked out separately
    - Public action used for creating issue comments

### Cleanup

1. If the workflow was run in this repository, perform the following steps:
    - Delete the new repository that was created
1. :exclamation: Do not delete or update the organization secrets used by this workflow

