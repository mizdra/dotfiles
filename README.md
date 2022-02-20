# dotfiles

## How to install

### Basic

Fetch the latest dotfiles from https://github.com/mizdra/dotfiles and install them.

```bash
sh -c \"$(curl -fsLS chezmoi.io/get)\" -- init --apply mizdra
```

### Visual Studio Code Remote - Containers

To save installation time, use [`--depth`](https://www.chezmoi.io/reference/commands/init/#-depth-depth) option.

`.vscode/settings.json`:

```json
{
  "dotfiles.installCommand": "sh -c \"$(curl -fsLS chezmoi.io/get)\" -- init --apply --depth=1 mizdra"
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
