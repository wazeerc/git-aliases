# Git Aliases for PowerShell

Simple git aliases for PowerShell inspired by Oh My Zsh, making your git workflow faster and more efficient.

## Features

- 🚀 **Fast git commands** - Short aliases for common git operations
- 🔧 **Simple setup** - Just copy and paste into your PowerShell profile
- 📝 **Oh My Zsh inspired** - Familiar aliases for Zsh users
- 🪟 **Windows friendly** - Works seamlessly with PowerShell

## Installation

### Simple Copy & Paste Setup

1. **Open your PowerShell profile for editing**:
   ```powershell
   notepad $PROFILE
   ```

   **💡 Helpful hints:**
   - If the file doesn't exist, PowerShell will ask if you want to create it - click "Yes"
   - You can also use VS Code: `code $PROFILE`
   - To see where your profile is located: `echo $PROFILE`
   - Common locations:
     - Windows PowerShell 5.1: `Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1`
     - PowerShell 7+: `Documents\PowerShell\Microsoft.PowerShell_profile.ps1`

2. **Copy the aliases**: Open [`git-aliases.md`](git-aliases.md) and copy all the PowerShell code from the "PowerShell Code" section

3. **Paste into your profile**: Paste the copied code at the end of your PowerShell profile file

4. **Save and reload**: Save the file and restart PowerShell or run:
   ```powershell
   . $PROFILE
   ```

That's it! All git aliases are now available in your PowerShell sessions.

## What You Get

28 useful git aliases including:
- **Basic commands**: `ga` (add), `gst` (status), `gcmsg` (commit with message)
- **Branch operations**: `gb` (branch), `gcb` (checkout new branch), `gco` (checkout)
- **Remote operations**: `ggl` (pull current branch), `ggp` (push current branch)
- **Log viewing**: `glo` (oneline log), `gln 5` (last 5 commits)
- **And many more!**

See [`git-aliases.md`](git-aliases.md) for the complete list with descriptions.

## Usage Examples

```powershell
# Quick workflow
gst              # Check status
ga .             # Add all files
gcmsg "Fix bug"  # Commit with message
ggp              # Push to current branch

# Branch management
gcb new-feature  # Create and switch to new branch
gco main         # Switch back to main
gbd old-branch   # Delete branch

# Viewing history
glo              # See recent commits
gln 5            # See last 5 commits
gd               # See what changed
```

## Requirements

- PowerShell 5.1 or higher
- Git installed and available in PATH

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Credits

Inspired by the [Oh My Zsh git plugin](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/git/).