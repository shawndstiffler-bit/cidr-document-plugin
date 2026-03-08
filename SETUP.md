# CIDR Document Plugin - New Machine Setup

## Prerequisites
- Claude Code installed
- Git installed
- GitHub CLI (`gh`) installed — `winget install GitHub.cli`

## Steps

### 1. Authenticate with GitHub (if not already)
```bash
gh auth login --web -p https
```

### 2. Clone the repo
```bash
git clone https://github.com/shawndstiffler-bit/cidr-document-plugin ~/Documents/cidr-document-plugin
```

### 3. Symlink into Claude Code plugins
```bash
mkdir -p ~/.claude/plugins/local
ln -s ~/Documents/cidr-document-plugin ~/.claude/plugins/local/cidr-document-format
```

### 4. Restart Claude Code
Close and reopen Claude Code so it picks up the new plugin.

## Verify
Ask Claude Code to create any CIDR document — it should automatically apply the brand formatting.

## Keeping in Sync
After making changes on either machine:
```bash
# On the machine where you made changes
cd ~/Documents/cidr-document-plugin
git add -A && git commit -m "Update skill" && git push

# On the other machine
cd ~/Documents/cidr-document-plugin
git pull
```
