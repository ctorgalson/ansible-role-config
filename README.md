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
| `config_compiz_config_file_name` | `compiz.profile` | The name of the copy of the Compiz `*.ini` file in the `dotfiles` repository. |
| `config_compiz_use_ini_backend` | `True` | Whether or not to _use_ the Compiz ini backend--if set to `False`, no Compiz configuration or settings will be attemted. |
| `config_dotfiles_dir_name` | `dotfiles` | The name of the directory to clone the `dotfiles` repo to (corresponds to the last directory in `dest` in and Ansible Git module task. |
| `config_dotfiles_repo` | `https://github.com/ctorgalson/dotfiles.git` | The url to a dotfiles repo (mine probably won't be that useful to you). |
| `config_home_dir` | `/Users` | The home directory on the current system--the default corresponds to macOS directory structure; change to `/home` on most linux distros. |
| `config_linked_dotfiles` | `[]` | The specific dotfiles in the `dotfiles` repo to symlink into users' home directories. |
| `config_users` | `[]` | The list of users to run this role for. |

## License

MIT
