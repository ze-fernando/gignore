# gignore

A simple and lightweight CLI for generating `.gitignore` files from [gitignore.io](https://www.toptal.com/developers/gitignore/api) templates.

Instead of manually searching for `.gitignore` templates, just tell `gignore` which technologies or tools your project uses.

## Installation

Install globally with `pipx`:

```bash
pipx install gignore-cli
```

You can also install it with `pip`:

```bash
pip install gignore-cli
```

## Usage

Generate a `.gitignore` for a Python project:

```bash
gignore python
```

You can combine multiple templates by separating them with commas:

```bash
gignore python,node
```

For example, for a project using Python, Node.js and VS Code:

```bash
gignore python,node,vscode
```

The generated `.gitignore` is created in the **current working directory**.

### Help

Display the available options and examples:

```bash
gignore --help
```

or:

```bash
gignore -h
```

## Warning

If a `.gitignore` already exists in the current directory, **gignore will overwrite it**.

Make sure you do not have important custom rules in the existing file before running the command.

## Examples

### Python project

```bash
mkdir my-project
cd my-project

gignore python
```

### Full-stack project

```bash
gignore python,node,vscode
```

### Multiple environments

```bash
gignore python,windows,macos,linux
```

## How it works

`gignore` sends the requested templates to gitignore.io and uses the returned content to create the `.gitignore` file.

For example:

```bash
gignore python,node
```

requests the `python` and `node` templates and combines their rules into the generated `.gitignore`.

## Features

- Simple command-line interface
- Supports multiple templates
- Generates `.gitignore` in the current directory
- Built-in `--help`
- Clear terminal output using [Rich](https://github.com/Textualize/rich)
- Uses gitignore.io templates
- Lightweight and easy to use

## Development

Clone the repository:

```bash
git clone https://github.com/ze-fernando/gignore.git
cd gignore
```

Install the development dependencies:

```bash
pdm install
```

Run the CLI locally:

```bash
pdm run python -m gignore.main python,node
```

Build the package:

```bash
pdm build
```

The generated packages will be available in the `dist/` directory.

## License

This project is licensed under the MIT License.
