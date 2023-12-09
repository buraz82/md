
# Daytona Workspaces Documentation

## Introduction
This documentation provides a thorough guide to managing workspaces in Daytona. Workspaces in Daytona are virtual machines hosted remotely, functioning like cloud-based laptops for development. 

## Getting Started with Daytona Workspaces

### Accessing Daytona
1. **Login**: To start, log in to your Daytona installation. If you don't have one, refer to the installation part of the documentation to set up your own Daytona instance.
2. **Navigating to Dashboard**: Once logged in, navigate to the URL you set up during installation to access the Daytona dashboard.

### Workspaces Overview
- **Location in Dashboard**: On the left-hand side of the web dashboard, you'll find a section dedicated to workspaces.
- **Creating Workspaces**: Use the 'Create' button in the workspaces section to start setting up a new workspace.
- **List of Workspaces**: Your existing workspaces are listed, providing easy access and management options.

## Creating and Managing Workspaces

### Creation Process
1. **Starting Creation**: Click the 'Create' button to initiate the process.
2. **Importing Projects**: You will be prompted to import a project from a repository. Daytona connects to your Git provider (GitHub, GitLab, Bitbucket), displaying all your repositories.
3. **Using Public Repositories**: You can also enter a public URL to a repository you have access to.
4. **Initiating Workspace**: After selecting the repository, clicking 'Create' begins the process of spinning up your new workspace.

### Understanding Workspace States
- **Phases of Workspace Creation**: The creation process includes multiple phases such as 'Creating' or 'Initializing'.
- **Initializing**: This phase involves cloning the repository and installing necessary components.
- **Starting**: The final steps to get the workspace ready, including starting up services.

### Using Workspaces
- **Accessing Workspaces**: Each workspace is accessible through the dashboard, with options to open, stop, or delete.
- **Workspace Information**:
  - The name, status (indicated by color codes like green for started, purple for starting, red for stopped).
  - The linked Git repository and branch information.
  - Time and date of workspace creation.
- **Pin Workspaces**: For easy access, you can pin workspaces to the top of your list.

## Advanced Workspace Features

### Expanded Workspace Options
- **Changing IDE**: Option to open the workspace in a different IDE than the default.
- **Stopping and Deleting**: Easily stop or permanently delete workspaces. Deleting requires confirmation by typing the workspace's full name.
- **SSH Connection**: Connect to your workspace via SSH using a public key or an access token.

### Workspace Logs and Info
- **Logs**: Access real-time logs of your workspace's activities, providing insights into the ongoing processes.
- **Workspace Info**: Get detailed information like workspace ID and creation date.

## Conclusion
Daytona workspaces offer a flexible, cloud-based development environment that can be easily managed through the Daytona dashboard or CLI. This guide provides the essential knowledge to create, manage, and utilize these workspaces effectively.

---
**Note**: This documentation is based on the provided transcript, aiming to give a comprehensive understanding of Daytona's workspace functionalities.
