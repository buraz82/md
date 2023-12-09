
# Daytona.io Installation Documentation

This document provides detailed instructions for installing Daytona.io, a comprehensive development environment platform. The process includes setting up a host, configuring a domain, creating an OAuth App with an identity provider, and running the installation script.

## Requirements

### Host Specifications
- **Architecture**: x86_64 architecture Linux OS.
- **Minimum Hardware**:
  - 4 vCPU.
  - 16GB RAM.
  - 200GB disk space.
- **Network**:
  - Public IP required.
  - Open TCP ports: 80, 443, and 30000 (also TCP 6443 for Kubernetes cluster access).
- **Tested Distros**: Debian-based distributions (Ubuntu 22.04/23.04, Debian 12).

### Domain Configuration
- Registered domain with base domain and wildcard pointed to your host IP.
- DNS Records:
  - `domain name IN A host.ip`
  - `*.domain-name IN A host.ip`

### OAuth App
- Create an OAuth App with one of the following providers:
  - [GitHub OAuth App](https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/creating-an-oauth-app)
  - [GitLab OAuth App](https://docs.gitlab.com/ee/integration/oauth_provider.html)
  - [Bitbucket OAuth](https://support.atlassian.com/bitbucket-cloud/docs/use-oauth-on-bitbucket-cloud/)
- Configuration Values:
  - Homepage URL: `https://{{ domain-name }}`
  - Authorization callback URL: `https://id.{{ domain-name }}`

## Setup Process

1. **Clone the Installer**:
   ```
   git clone https://github.com/daytonaio/installer
   cd installer
   ```
2. **Run the Setup Script**:
   ```
   ./setup.sh
   ```
   - During the setup, you will be prompted to enter the following:
     - Domain (`URL`)
     - Identity Provider (`IDP`)
     - Client ID (`IDP_ID`)
     - Client Secret (`IDP_SECRET`)

### Identity Provider Configuration
- Depending on the chosen IDP, additional variables might be required:
  - `IDP_URL` (for `gitlabSelfManaged` or `githubEnterpriseServer`)
  - `IDP_API_URL` (for `githubEnterpriseServer`)

### Variables Table
| IdP                    | Variables Required                             |
|------------------------|------------------------------------------------|
| github, gitlab, bitbucket | URL, IDP, IDP_ID, IDP_SECRET                   |
| gitlabSelfManaged      | URL, IDP, IDP_ID, IDP_SECRET, IDP_URL          |
| githubEnterpriseServer | URL, IDP, IDP_ID, IDP_SECRET, IDP_URL, IDP_API_URL |

### CLI Setup Option
- Set values via CLI when running the script:
  ```
  URL="daytona.example.com" IDP="github" IDP_ID="changeme" IDP_SECRET="changeme" ./setup.sh
  ```

## Update Procedure
- To update an existing setup, rerun the `setup.sh` script with the latest version.
- Re-enter any variables if prompted, or use the CLI command with the necessary values.

## Restart/Cleanup
- To remove and restart the setup, use the `--remove` parameter with the setup script:
  ```
  ./setup.sh --remove
  ```
- Then, you can reinstall with the `--install` parameter.

---
This documentation is based on the provided instructions and transcript. It's intended to guide users through the process of installing and configuring Daytona.io on their systems.
