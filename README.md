# Ansible Role Config

This role is used for configuring various system and application
preferences and settings on macOS and Ubuntu for one or more users.

Currently, it is used to:

- Configure Compiz (Ubuntu)
- Place dotfiles in user directories (Ubuntu, macOS)

Planned additions include:

- Configure Dock applications (macOS)
- Auto import of `*.plist` files (macOS)
- `defaults.write` settings (macOS)
- More dotfiles (Ubuntu, macOS)

## Role Variables

| Variable name  | Default value | Description |
|----------------|---------------|-------------|
| `config_config_dir_name` | `.ansible-managed-config` | The name of the parent directory where the `dotfiles` repo should be cloned. |
| `config_dotfiles_dir_name` | `dotfiles` | The name of the directory to clone the `dotfiles` repo to (corresponds to the last directory in `dest` in and Ansible Git module task. |
| `config_dotfiles_repo` | `https://github.com/ctorgalson/dotfiles.git` | The url to a dotfiles repo (mine probably won't be that useful to you). |
| `config_home_dir` | `/Users` | The home directory on the current system--the default corresponds to macOS directory structure; change to `/home` on most linux distros. |
| `config_linked_dotfiles` | `[]` | The specific dotfiles in the `dotfiles` repo to symlink into users' home directories. Note that this should be an array of **paths** (relative to `~` to the files in question. E.g., for an ssh config file the path should be `.ssh/config` so that the file will be linked to `/home/username/.ssh/config`. |
| `config_ssh_config` | `True` | Whether or not to run the `ssh_config.yml` task and copy a file from a dotfiles repo to `/Users/username/.ssh/config`. |
| `config_users` | `[]` | The list of users to run this role for. |

## License

MIT
