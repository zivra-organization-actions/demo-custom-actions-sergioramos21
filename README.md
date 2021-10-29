# Custom actions

Demo repository for using custom actions in a workflow.

This demo uses a mix of public and private actions to create a repository in the organization from a new issue. For the private actions, a GitHub App token is used to authenticate since the `GITHUB_TOKEN` is scoped to the workflow repo only.

:exclamation: **This demo should be run from within this repository to avoid errors related to GitHub App credentials etc.**
- Please make sure to complete the **Cleanup** steps afterwards :house_with_garden:

## Usage 

### Create a new issue

1. In this repository, go to **Issues** and create a new issue based on the template
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
    - Private actions used to parse the issue and create a new repository in the organization
      - Private actions are checked out separately
    - Public action used for creating issue comments
    - Show the source code of the private actions used by the workflow (`action.yml` file, `index.js`, libraries used, ...)

### :house_with_garden: Cleanup

1. Delete the new repository that was created
1. :exclamation: Do not delete or update the organization secrets used by this workflow

