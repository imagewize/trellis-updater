# Trellis Updater

A Bash script to safely update your [Roots Trellis](https://roots.io/trellis/) installation while preserving your custom configurations.

## Features

- Creates a backup of your current Trellis directory
- Downloads the latest version of Trellis
- Generates a diff to see what would change
- Updates your Trellis files while preserving important configurations:
  - Vault files with passwords and sensitive data
  - WordPress site configurations
  - User configurations
  - Host configurations
  - Trellis CLI configuration
- Commits changes to your Git repository

## What This Script Preserves

The updater script specifically preserves the following files/directories:
- `.vault_pass`
- `.trellis/`
- `.git/`
- `.github/`
- `group_vars/all/vault.yml`
- `group_vars/development/vault.yml`
- `group_vars/development/wordpress_sites.yml`
- `group_vars/production/vault.yml`
- `group_vars/production/wordpress_sites.yml`
- `group_vars/staging/vault.yml`
- `group_vars/staging/wordpress_sites.yml`
- `group_vars/all/users.yml`
- `trellis.cli.yml`
- `hosts/` directory

## Usage

1. Edit the script to set your project slug:
```bash
# Set your project slug here like imagewize.com
PROJECT="your-site-name"
```

2. Make the script executable:
```bash
chmod +x updates/trellis-updater.sh
```

3. Run the script:
```bash
./updates/trellis-updater.sh
```

4. Review the changes in your Git repository before pushing them.

## Requirements

- Git
- Bash
- rsync

## License

MIT License. See [LICENSE.md](../LICENSE.md) for details.