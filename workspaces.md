## What are Workspaces?
A workspace is a self-contained development environment, pre-configured with the project’s source code, required dependencies, necessary tools, and extensions to optimize workflow for your development team.

Daytona workspaces simplify the setup and configuration of development environments, integrate various tools, automate repetitive tasks, and ensure a consistent experience across different teams and projects. By following established practices and automation, Development Environment Management ensures that all developers have access to a consistent, secure, and standardized environment, ultimately enhancing productivity and streamlining the software development process.

### Workspaces Overview
- **Location in Dashboard**: In the web dashboard, look for the 'Workspaces' section on the left-hand side.
- **Creating Workspaces**: Click the 'Create' button in the workspaces section to start a new workspace.
- **List of Workspaces**: View and manage your existing workspaces listed in this section.

### Accessing Daytona Workspaces
1. **Login**: Log in to your Daytona installation. If you don't have one, refer to the installation documentation to set up your Daytona instance.
2. **Navigating to Dashboard**: Once logged in, navigate to the URL you set up to access the Daytona dashboard.

## Creating Workspaces

### Creation Process
1. **Starting Creation**: Click 'Create' to import a project from a repository.
2. **Importing Projects**: You will be prompted to import a project from your Git provider (GitHub, GitLab, Bitbucket).
3. **Using Public Repositories**: Alternatively, enter a public URL to a repository you have access to.
4. **Initiating Workspace**: After selecting the repository, clicking 'Create' begins the workspace setup process.

### Creation States
- **Warming Up**: The initial phase where the virtual machine (VM) for your workspace is being started.
- **Initializing**: In this phase, Daytona clones the repository and starts installing necessary components based on your repository's configuration.
- **Starting**: Finalizing the setup, this phase involves spinning up all the services required for your workspace.
- **Opening IDE**: Depending on your settings, Daytona will open the workspace in the default or selected IDE.

## Managing Workspaces

### Accessing Workspace
- **Open in IDE** Click on the Workspace name to open it in the defualt IDE
- **SSH Connection**: Securely connect to your workspace via SSH using a public key or an access token.
- **Workspace Manupulation**: Clicking on the expanded menu of a workspace '...' Easily stop or delete workspaces. Deletion requires retypoing the name to confirm for security.
- **Workspace Status**:color-coded: green for started, purple for starting, red for stopped.
- **Workspace Status**: Linked Git repository and branch information can be found below every Worksapce's name


### Expanded Workspace Options
Information that can be found hitting the expanded view of a workspace
- **Pin Workspaces**: Pin frequently used workspaces for quick access.
- **Changing IDE**: IF you would like to open the Workspace in a different IDE that set by default, click 'Open' to Switch between different IDEs for opening your workspace.
- **Workspace Creation Date**: To find the time and date of creation, click on Info.


