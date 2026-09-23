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

### Adding templates

If a `.gitignore` already exists, `gignore` will ask whether you want to add the generated rules to the existing file.

For example:

```bash
gignore python,node
```

You can confirm the operation interactively, and the new rules will be added to the existing `.gitignore`.

### Overwriting an existing file

To overwrite an existing `.gitignore` without confirmation, use `-o` or `--override`:

```bash
gignore python --override
```

or:

```bash
gignore python -o
```

### List available templates

Display all available templates:

```bash
gignore --list
```

or:

```bash
gignore -l
```

### Find templates

Search for templates by name:

```bash
gignore --find python
```

or:

```bash
gignore -f python
```

You can use this to discover the correct template name before generating your `.gitignore`.

### Help

Display the available options and examples:

```bash
gignore --help
```

or:

```bash
gignore -h
```

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

### Find a template

```bash
gignore -f django
```

### List all templates

```bash
gignore -l
```

### Overwrite an existing `.gitignore`

```bash
gignore python,node -o
```

## How it works

`gignore` sends the requested templates to gitignore.io and uses the returned content to create or update the `.gitignore` file.

For example:

```bash
gignore python,node
```

requests the `python` and `node` templates and combines their rules into the generated `.gitignore`.

If a `.gitignore` already exists, the generated rules can be added to the existing file. Use `--override` when you want to replace the existing file instead.

## Features

- Simple command-line interface
- Supports multiple templates
- Search for available templates
- List all available templates
- Add generated rules to an existing `.gitignore`
- Optional overwrite with `--override`
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
