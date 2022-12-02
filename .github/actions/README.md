# eScience Hackweek Jupyterbook Template GitHub Actions

This folder contains continuous integration workflows to perform a variety of tasks such as checking for spelling errors and broken links, ensuring HTML is generated without errors, and publishing the website.

## Actions

the `actions/` subfolder contains common [composite actions steps](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action) that any workflow can use.

#### [setupconda](./setupconda/action.yaml)
Steps to configure conda environment required to build the website.

#### [buildresources](./buildresources/action.yaml)
Steps to build the hackweek landing webpage and JupyterBook.


## Workflows

The `workflows/` subfolder contains continuous integration workflows

#### [deploy.yaml](../workflows/deploy.yaml)
Render and publish the websites (JupyterBook and landing page) to GitHub Pages

#### [netlifypreview.yaml](../workflows/netlifypreview.yaml)
Creates public preview, via [netlify](https://jupyterbook.org/publish/netlify.html), of changes by building from a PR

## Security

It's desirable for hackweek websites to have contributions from anyone, so the website repository should allow for changes via pull requests from forks. By default workflows running off forked repositories do not have access to secrets, but [following security best practices](https://securitylab.github.com/research/github-actions-preventing-pwn-requests/) you can require adding a label to a pull request in order to run a workflow that requires secrets. For an example, see the [netlifypreview.yaml](./actions/workflows/netlifypreview.yaml) workflow.
