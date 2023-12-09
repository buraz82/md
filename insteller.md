
# Comprehensive Installation Guide for Daytona.io

Welcome to the in-depth guide for installing Daytona.io. This guide is designed to walk you through each step of the installation process, explaining the details so you can set up your development environment confidently. Let's dive in!

## Before You Begin: Preparation Steps

### Setting Up the Right Environment
- **Choose a Compatible Computer**: Ensure you're using a Linux-based system, ideally running Ubuntu 22.04 or 23.04, or Debian 12.
- **Hardware Requirements**:
  - **CPU**: Minimum 4 virtual CPUs. Think of these as the engine of your setup.
  - **Memory**: At least 16GB RAM. This is like having a larger desk to work on.
  - **Storage**: Minimum 200GB disk space, to store all your projects and tools.
- **Network Setup**:
  - Ensure your system has a public IP address.
  - Open specific TCP ports (80, 443, 30000, and optionally 6443) for web access and Kubernetes interaction.

### Domain and DNS Configuration
- **Own a Domain**: You need a registered domain. This will be the address for your Daytona instance.
- **DNS Setup**:
  - Point your base domain (e.g., `mydomain.com`) to your host's IP address.
  - Set up a wildcard DNS record (e.g., `*.mydomain.com`) to the same IP. This allows for creating subdomains.

### Identity Provider Setup
- **Choose an OAuth Provider**: GitHub, GitLab, or Bitbucket. This is where you'll authenticate users for Daytona.
- **OAuth App Configuration**:
  - Create an OAuth application on your chosen platform.
  - Set the Homepage URL to `https://your-domain-name`.
  - Set the Authorization callback URL to `https://id.your-domain-name`.
  - Note down the Client ID and Secret provided by the OAuth app. These are crucial for the setup.

## Installation Steps

### Getting the Installer
1. **Clone the Installer Repository**:
   Open your terminal and execute:
   ```
   git clone https://github.com/daytonaio/installer
   cd installer
   ```
   This command downloads the necessary scripts to start the installation.

2. **Initiate the Setup**:
   Begin the installation by running:
   ```
   ./setup.sh
   ```
   This script is the key to installing Daytona on your machine.

### During the Setup
- The setup script will prompt you for various details:

### Entering Your Domain Name (URL)
- **Prompt**: `Enter app hostname (valid domain) [URL]:`
- **Action**: Type in the domain name you registered and set up in your DNS settings. For example, if your domain is `example.com`, enter `example.com` and press Enter.
- **Explanation**: This domain will be used as the primary address for accessing your Daytona instance.

### Choosing Your Identity Provider (IDP)
- **Prompt**: `Identity Providers (IdP) available [IDP]:`
- **Action**:
  1. You'll see a list of identity providers (e.g., GitHub, GitLab, Bitbucket).
  2. Type the number corresponding to the provider you have set up your OAuth app with and press Enter.
- **Explanation**: This step links Daytona to the authentication service you chose, allowing users to log in through it.

### Entering OAuth Application Details
- **Client ID Prompt**: `Enter IdP Client ID [IDP_ID]:`
- **Client Secret Prompt**: `Enter IdP Client Secret (IDP_SECRET) (input hidden):`
- **Action**:
  - Enter the Client ID and Client Secret provided by your OAuth application. The Client Secret input will be hidden for security.
- **Explanation**: These details authenticate Daytona with your identity provider, ensuring secure login functionality.

### Additional Identity Provider Details (If Required)
- **For GitLab Self-Managed or GitHub Enterprise Server**:
  - **IDP URL Prompt**: `Enter IdP URL [IDP_URL]:`
  - **IDP API URL Prompt** (GitHub Enterprise Server only): `Enter IdP API URL [IDP_API_URL]:`
  - **Action**: Enter the base URL of your self-managed GitLab or GitHub Enterprise Server instance and, if applicable, the API URL for GitHub Enterprise Server.
  - **Explanation**: These URLs ensure that Daytona can communicate correctly with your self-hosted identity provider.

### Expert Mode: Command Line Setup
- If you're comfortable with terminal commands, you can pre-set all values in one command line:
  ```
  URL="your-domain.com" IDP="github" IDP_ID="your-client-id" IDP_SECRET="your-client-secret" ./setup.sh
  ```
  This method allows for a quicker setup by providing all necessary details upfront.

## Post-Installation

### Updating Daytona
- Keeping Daytona up-to-date is as simple as re-running the setup script with the latest version. It's like refreshing your installation to the newest state.

### Restarting or Cleaning Up
- If you need to remove your Daytona setup and start over, use the following command:
  ```
  ./setup.sh --remove
  ```
- To reinstall, simply run the setup script again.

---
This guide is based on detailed instructions and insights from the installation process of Daytona.io. It aims to provide a clear and comprehensive path for setting up and maintaining your Daytona environment. If you encounter any issues or have specific questions, the Daytona community and support resources are available to assist you.
