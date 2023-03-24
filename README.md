# Overview
A repository consisting of various pipeline templates. This supports the Paved Road devsecops approach with a 1:many model. This also enforces proper deployment behaviours as local pipelines cannot override the templates. 

### Caveats
* `.github` dir should have required approvers

### Called Workflows
* Templates designed to be stored centrally in a repository
* Repo must be either private or public
    - if private (preferred), create deploy keys and store as described in github docs
* Stored in the `.github/workflows` dir as required by GH
* Scans code for compliance using Chekhov (for AWS pipelines)
* Requires the Github OpenID identity provider to be configured in AWS

### Calling workflows
* Stored in the `.github/workflows` folder of your code repo
* Store `SSH_KEY` as a secret on the repo
* Store platform relevant secrets (Cloudflare tokens, or AWS roles)
