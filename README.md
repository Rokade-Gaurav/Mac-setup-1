# mac-setup
```markdown
# mac-setup

This script sets up a macOS development environment by installing Homebrew and some common packages.

## Installation

Run the following script to set up your environment:

```bash
#!/bin/bash

# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Add Homebrew to PATH
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"

# Update Homebrew
brew update

# Install some common packages
brew install git
brew install wget
brew install node
brew install python
brew install docker

# Start Docker service
brew services start docker

# Add current user to the docker group to run docker without sudo
sudo dscl . -append /Groups/docker GroupMembership $(whoami)

# Inform the user to restart the terminal for changes to take effect
echo "Please restart your terminal for the changes to take effect."
```

## Notes

- Ensure you have the necessary permissions to install software on your macOS.
- Restart your terminal after running the script to apply the changes.
```
