# Daytona CLI Tool Documentation

## General Flags
```
Usage:
  daytona [flags]
  daytona [command]

Available Commands:
  code              Starts the workspace in VS Code
  create            Initializes a workspace with the given git repository or a picked template
  delete            Commands the workspace given by ID to be destroyed
  env               Lists or manipulates environment variables
  help              Help about any command
  ide               Sets a default IDE for the current user
  info              Retrieves the information of workspace given by ID
  list              Shows a list of workspaces by the current user and team
  login             Authenticates the user using the browser
  logout            Logs user profile out of the CLI
  pin               Commands the workspace given by ID to become pinned
  profile           Lists available profiles to choose from
  share             Commands the workspace given by ID to become shared
  ssh               Connect to the workspace using Secure Shell
  start             Commands the workspace given by ID to start
  stop              Commands the workspace given by ID to stop
  team              Lists available teams to choose from
  unpin             Commands the workspace given by ID to become unpinned
  unshare           Commands the workspace given by ID to become unshared
  version           Returns the version of your Daytona CLI

Flags:
  -h, --help   help for daytona

Use "daytona [command] --help" for more information about a command.
```

## Command: code
```
Usage:
  daytona code [flags]

Flags:
  -h, --help         help for code
  -i, --ide string   Specify the IDE (e.g., 'vscode' or 'browser')
```

## Command: create
```
Usage:
  daytona create [flags]

Flags:
  -c, --code   Open the project your default IDE after creating the workspace
  -h, --help   help for create
```

## Command: delete
```
Usage:
  daytona delete [flags]

Flags:
  -o, --all    Apply command to all workspaces
  -h, --help   help for delete
```

## Command: env
```
Usage:
  daytona env [flags]
  daytona env [command]

Available Commands:
  remove      Removes the environment variable specified by key

Flags:
  -h, --help   help for env

Use "daytona env [command] --help" for more information about a command.
```

## Command: help
```
Usage:
  daytona help [command] [flags]

Flags:
  -h, --help   help for help
```

## Command: ide
```
Usage:
  daytona ide [flags]

Flags:
  -h, --help          help for ide
  -n, --name string   Specify IDE by name
```

## Command: info
```
Usage:
  daytona info [flags]

Flags:
  -h, --help   help for info
```

## Command: list
```
Usage:
  daytona list [flags]

Aliases:
  list, ls

Flags:
  -h, --help   help for list
```

## Command: login
```
Usage:
  daytona login [flags]

Flags:
  -h, --help   help for login
```

## Command: logout
```
Usage:
  daytona logout [flags]

Flags:
  -h, --help   help for logout
```

## Command: pin
```
Usage:
  daytona pin [flags]

Flags:
  -h, --help   help for pin
```

## Command: profile
```
Usage:
  daytona profile [flags]
  daytona profile [command]

Available Commands:
  active      Retrieves the ID of the currently active profile
  info        Displays information about the active profile
  list        Lists available profiles
  new         Creates a new profile
  set-name    Updates the name of the active profile to one given by argument
  set-url     Updates the base URL of the active profile to one given by argument
  use         Updates the active profile to one given by argument

Flags:
  -h, --help   help for profile

Use "daytona profile [command] --help" for more information about a command.
```

## Command: share
```
Usage:
  daytona share [flags]

Flags:
  -o, --all    Apply command to all workspaces
  -h, --help   help for share
```

## Command: ssh
```
Usage:
  daytona ssh [flags]

Flags:
  -h, --help   help for ssh
```

## Command: start
```
Usage:
  daytona start [flags]

Flags:
  -o, --all    Apply command to all workspaces
  -h, --help   help for start
```

## Command: stop
```
Usage:
  daytona stop [flags]

Flags:
  -o, --all    Apply command to all workspaces
  -h, --help   help for stop
```

## Command: team
```
Usage:
  daytona team [flags]

Flags:
  -h, --help          help for team
  -n, --name string   Specify team name
```

## Command: unpin
```
Usage:
  daytona unpin [flags]

Flags:
  -h, --help   help for unpin
```

## Command: unshare
```
Usage:
  daytona unshare [flags]

Flags:
  -o, --all    Apply command to all workspaces
  -h, --help   help for unshare
```

## Command: version
```
Usage:
  daytona version [flags]

Flags:
  -h, --help   help for version
```

