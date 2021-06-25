# CIS Web Services Static Site Hosting
## GitHub Actions Deployment Process

### Setup for Repo Passing Files for Hosting
(time estimate, less than 5 minutes)

* The owner/manager of a repository to be hosted provides editing access to us.
* We assess the repo for the appropriate action
  * Plain static files (HTML, CSS & JS)
  * Static site that requires a build/compile process
    * Check for `NPM` or `Yarn` usage for build process
* Based on assessment we add a customized `.yaml` file to `.github/workflows` to handle passing the file to our repo.
* We add to the repositories secrets any variables for the action we want protected, including but not limited to a token from the `webservices-static` repository that allows access for the action
* Create a PR to merge our changes into the primary branch of the repo

### Setup in the Webservices-static Repo

* Create a branch named the same as referenced as key `destination_branch` in the provided action file.
* whatever steps are needed for urls and such

### Deploying Updated Files

  * PR is created on the passed files branch
  * PR is reviewed to verify files have not been written where they were not expected (like overwriting someone else's files)
  * PR merged into our standard deploy/release process

## Before Implementation

* Lock down the `main` branch so that only we can modify it via approved PR to prevent accidental and/or malicious overwrites
* Create a GitHub action to automatically generate a PR for when files are written to the repo and assign us reviewers
  * Possible future enhancement, add action/bot for auto checking and approving PRs
* Setup additional notifications of PRs/files added as needed
