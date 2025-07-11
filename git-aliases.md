# Git Aliases for PowerShell

:octocat: PowerShell Git aliases inspired by Oh My Zsh.

## Available Aliases

| Alias | Command | Description |
|-------|---------|-------------|
| `ga` | `git add` | Add files to staging area |
| `gaa` | `git add --all` | Add all files to staging area |
| `gb` | `git branch` | List branches |
| `gba` | `git branch -a` | List all branches (including remote) |
| `gbd` | `git branch -d` | Delete branch |
| `gcb` | `git checkout -b` | Create and checkout new branch (Use `Remove-Alias gcb -Force` to remove the default pwsh alias `Get-Clipboard`) |
| `gcmsg` | `git commit -m` | Commit with message |
| `gco` | `git checkout` | Checkout branch/file |
| `gcp` | `git cherry-pick` | Cherry-pick commit |
| `gd` | `git diff` | Show changes |
| `gds` | `git diff --staged` | Show staged changes |
| `gf` | `git fetch` | Fetch from remote |
| `ggl` | `git pull origin $(current_branch)` | Pull from origin/current branch |
| `ggp` | `git push origin $(current_branch)` | Push to origin/current branch |
| `gl` | `git pull` | Pull from remote |
| `glgm` | `git log --graph --max-count=10` | Show graph log (last 10) |
| `gln <n>` | `git log -n <number> --oneline` | Show last N commits in oneline format (e.g., `gln 5`) |
| `glo` | `git log --oneline --decorate` | Show one-line log |
| `gm` | `git merge` | Merge branch |
| `gp` | `git push` | Push to remote |
| `gpf` | `git push --force` | Force push |
| `gr` | `git remote` | Manage remotes |
| `grb` | `git rebase` | Rebase branch |
| `grv` | `git remote -v` | Show remotes with URLs |
| `gsh` | `git show` | Show commit details |
| `gst` | `git status` | Show repository status |
| `gstl` | `git stash list` | List stashes |

## PowerShell Code

Copy and paste the following code into your PowerShell profile:

```powershell
# Git Aliases (Oh My Zsh inspired)

# Helper function to get current branch
function Get-CurrentBranch {
    $branch = git branch --show-current 2>$null
    if ($branch) { return $branch }
    return "main"
}

# Basic git commands
function ga { git add @args }
function gaa { git add --all @args }
function gb { git branch @args }
function gba { git branch -a @args }
function gbd { git branch -d @args }
function gcb { git checkout -b @args }
function gcmsg { git commit -m @args }
function gco { git checkout @args }
function gcp { git cherry-pick @args }

# Diff commands
function gd { git diff @args }
function gds { git diff --staged @args }

# Fetch and pull/push
function gf { git fetch @args }
function ggl {
    $currentBranch = Get-CurrentBranch
    git pull origin $currentBranch @args
}
function ggp {
    $currentBranch = Get-CurrentBranch
    git push origin $currentBranch @args
}
function gl { git pull @args }

# Log commands
function glgm { git log --graph --max-count=10 @args }
function glo { git log --oneline --decorate @args }
function git-log-n {
    param (
        [int]$n = 10
    )

    if ($n -le 0) {
        Write-Warning "Number of commits must be greater than 0"
        return
    }

    git log -n $n --oneline
}
Set-Alias -Name gln -Value git-log-n

# Merge and push
function gm { git merge @args }
function gp { git push @args }
function gpf { git push --force @args }

# Remote commands
function gr { git remote @args }
function grb { git rebase @args }
function grv { git remote -v @args }

# Show and status
function gsh { git show @args }
function gst { git status @args }
function gstl { git stash list @args }
```
