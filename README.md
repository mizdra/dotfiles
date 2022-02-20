# dotfiles

## How to install

### Basic

Fetch the latest dotfiles from https://github.com/mizdra/dotfiles and install them.

```bash
sh -c \"$(curl -fsLS chezmoi.io/get)\" -- init --apply mizdra
```

### Visual Studio Code Remote - Containers

`dotfiles.installCommand` must specify the path to the executable file.

`.vscode/settings.json`:

```json
{
  "dotfiles.repository": "mizdra/dotfiles",
  "dotfiles.targetPath": "~/dotfiles",
  "dotfiles.installCommand": "~/dotfiles/install.sh",
}
```

### Dockerfile
To save disk space, use [`--one-shot`](https://www.chezmoi.io/reference/commands/init/#-one-shot) option.

`Dockerfile`:

```dockerfile
RUN sh -c \"$(curl -fsLS chezmoi.io/get)\" -- init --apply --one-shot mizdra
```

### Manual
Using the [`-S`](https://www.chezmoi.io/reference/command-line-flags/global/#-s-source-directory) option, you can install from any location.

```bash
git clone git@github.com:mizdra/dotfiles.git ~/dotfiles
sh -c "$(curl -fsLS chezmoi.io/get)" -- init --apply -S ~/dotfiles
```

## How to update

```bash
chezmoi update
```
