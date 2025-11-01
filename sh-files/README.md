# Installation

To use these scripts from anywhere in your terminal, add them to your PATH.

### Step 1: Make scripts executable

The scripts should already be executable, but if needed:

```bash
cd /Users/nhannguyen/projects/personal-scripts/lol-scripts
chmod +x sh-files/*.sh
chmod +x sh-files/*
```

### Step 2: Add to PATH

Choose one of the following methods:

#### Method 1: Add `sh-files` directory to PATH (Recommended)

**For Zsh (default on macOS):**

1. Open your zsh configuration file:
   ```bash
   nano ~/.zshrc
   ```
   
   Or if you prefer:
   ```bash
   open -e ~/.zshrc
   ```

2. Add the following line at the end:
   ```bash
   export PATH="$PATH:/Users/nhannguyen/projects/personal-scripts/lol-scripts/sh-files"
   ```

3. Reload your shell configuration:
   ```bash
   source ~/.zshrc
   ```

**For Bash:**

1. Open your bash configuration file:
   ```bash
   nano ~/.bash_profile
   ```
   
   Or:
   ```bash
   open -e ~/.bash_profile
   ```

2. Add the following line at the end:
   ```bash
   export PATH="$PATH:/Users/nhannguyen/projects/personal-scripts/lol-scripts/sh-files"
   ```

3. Reload your shell configuration:
   ```bash
   source ~/.bash_profile
   ```

#### Method 2: Create symlinks in `/usr/local/bin`

1. Create symlinks:
   ```bash
   sudo ln -s /Users/nhannguyen/projects/personal-scripts/lol-scripts/sh-files/kill-port /usr/local/bin/kill-port
   sudo ln -s /Users/nhannguyen/projects/personal-scripts/lol-scripts/sh-files/check-process-ports /usr/local/bin/check-process-ports
   ```

2. Verify they work:
   ```bash
   kill-port --help
   check-process-ports
   ```

### Step 3: Verify Installation

Test that the scripts are available:

```bash
# Check if scripts are in PATH
which kill-port
which check-process-ports

# Test the scripts
kill-port 3000        # (Will show error if port 3000 is not in use)
check-process-ports   # Should show ports for java, python, node
```

## Troubleshooting

### Scripts not found after adding to PATH

1. Make sure you've reloaded your shell:
   ```bash
   source ~/.zshrc    # For zsh
   # or
   source ~/.bash_profile    # For bash
   ```

2. Verify the PATH is set correctly:
   ```bash
   echo $PATH | grep lol-scripts
   ```

3. Check if the scripts are executable:
   ```bash
   ls -l /Users/nhannguyen/projects/personal-scripts/lol-scripts/sh-files/
   ```

### Permission denied error

Make the scripts executable:
```bash
chmod +x /Users/nhannguyen/projects/personal-scripts/lol-scripts/sh-files/*
```

## Notes

- Make sure to update the path in the installation instructions if you move this repository to a different location.
- The scripts require `lsof` command which is available by default on macOS and most Linux distributions.

