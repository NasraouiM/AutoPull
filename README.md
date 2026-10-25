# AutoPull

AutoPull is a Python script that manages a configuration file and automates the process of updating multiple git repositories using the `git` command.

## Prerequisites

- Python 3.x
- Git installed and configured

## Getting Started

1. Clone the repository or download the `AutoPull.py` file to your local machine.

2. Configure the `AutoPull.conf` file:
   You need to run the script first to create the $HOME/.config/AutoPull/AutoPull.conf automatically.
   - If the `AutoPull.conf` file doesn't exist, the script will recreate it with default settings, then you can edit it.

3. Run the script:

   ```
   python AutoPull.py
   ```

   The script will read the configuration file, retrieve the repository paths and the allowed paths in order to compare them and add new folders if they are
   detected, and then, it will update the allowed repositories using the `git pull` command.

4. Review the output:

   - The script will provide updates and status messages for each repository being updated.
   - If the `VerboseGit` setting is enabled, detailed output from the `git pull` command will be displayed.

## Configuration

1. The configuration file (`AutoPull.conf`) is used to specify the settings for AutoPull. Here's an example of the default configuration:

```
#This file should be modified with caution, misconfiguration can result in complete disfunction of the program
#The src value should point to the folder containing all the git repositories that the user wishes to Auto-Update

[Settings]

src = /path/to/repositories/
VerboseGit = on
Debugging = off
```

- `src`: The path of the folder containing the git repositories to update.
- `VerboseGit`: Determines whether to display verbose output from the `git pull` command.
- `Debugging`: Enables or disables debugging mode for additional output and information.

2. `AllowedRepos` file contains all the repositories that AutoPull detected in the src folder specified in `AutoPull.conf`. The user can disable the update of a
specific Git repository by changing the `Allowed` value stated next to the repository's path in this file. As a result, the script will ignore this repository.

N.B : 
- AutoPull will detect new folders and ask the user if they want to allow the Auto-update .
- You can include folders not present in src by adding their path in `AllowedRepos` followed by ` = Allowed`. Don't change the file structure.

## License

This project is licensed under the [MIT License](LICENSE).
```

Feel free to modify and customize this README file according to your project's specific requirements and guidelines.
