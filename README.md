# flutter-generator

A CLI generator for flutter stateless/stateful widget page, router and bloc.

## Install

```console
$ npm install -g flutter-generator
```

## Usage

The most basic command runs a wizard to create a page.

```console
$ fg
```

**Note**: Names can be given in any format (slug-case, camelCase, PascalCase, UPPERCASE, lowercase etc.).

#### stateful widget page

Directly create a component based on the current settings with stateful widget.

```console
$ fg stateful-page <name>
```

Arguments:

- `name`: The name you want to use for the page.

Options:

- `-d, --destination <destination>`: Override the destination for component.
- `-p, --template-path <template-path>`: Override template path.
- `-t, --template <template>`: Override template type. By default it uses the 'pages' folder from the template path. With this option you can use a different template folder.
- `-f, --force`: Force creation of a page. By default it's impossible to create a page if the destination path doesn't exist. This option forces the creation of a page and will generates the destination folders if they don't exist.

Examples:

```console
$ fg stateful-page  home-page
$ fg stateful-page  setting-page -d ./my-component/ui
$ fg stateful-page  detail-page -d ./src/widget/players/ -t details -f
```

The generated file will be

```console
$ home_page.dart
```

#### stateless widget page

Directly create a component based on the current settings with stateless widget.

```console
$ fg stateless-page <name>
```

Arguments:

- `name`: The name you want to use for the page.

Options:

- `-d, --destination <destination>`: Override the destination for page.
- `-p, --template-path <template-path>`: Override template path.
- `-t, --template <template>`: Override template type. By default it uses the 'pages' folder from the template path. With this option you can use a different template folder.
- `-f, --force`: Force creation of a page. By default it's impossible to create a page if the destination path doesn't exist. This option forces the creation of a page and will generates the destination folders if they don't exist.

Examples:

```console
$ fg stateless-page  home-page
$ fg stateless-page  setting-page -d ./my-component/ui
$ fg stateless-page  detail-page -d ./src/widget/players/ -t details -f
```

The generated file will be

```console
$ home_page.dart
```

#### bloc

Directly create a bloc module based on the current settings.

```console
$ fg bloc <name>
```

Arguments:

name: The name you want to use for the bloc module.
Options:

- `-d, --destination <destination>`: Override the destination for bloc module.
- `-p, --template-path <template-path>`: Override template path.
- `-t, --template <template>`: Override template type. By default it uses the 'bloc' folder from the template path. With this option you can use a different template folder.
- `-f, --force`: Force creation of a bloc. By default it's impossible to create a bloc if the destination path doesn't exist. This option forces the creation of a bloc and will generates the destination folders if they don't exist.

Examples:

```
$ fg bloc user
$ fg bloc shopping-cart -d ./modules
$ fg bloc Car -t bloc
```

The generated file will be

```console
$ name_bloc.dart
```

#### settings

Set or display settings. Without any options it will display the settings. By default it will set the settings locally in a .fluttergenerator file.
You can also set global settings by using the global option `-g --global`.

```console
$ fg settings
```

Options:

- `-v, --view-destination <destination>`: Set default view destination.
- `-c, --component-destination <destination>`: Set default component destination.
- `-s, --store-destination <destination>`: Set default store destination.
- `-t, --template-path <template-path>`: Set template path.
- `-l, --log`: Log global or local settings depending on the global flag.
- `-g, --global`: Set global settings.

Examples:

```console
$ fg settings -l
$ fg settings -v ./view -c ./widgets -s ./models/store -t ./template
$ fg settings -g -c ./widgets
```

#### reset

Reset global settings to the defaults.

```console
$ fg reset
```

#### show-templates

Open the default template directory. The default templates can be edited to fit your needs.

```console
$ fg show-templates
```

#### copy-templates

Copy the default templates to another directory. This is handy when you want to customize the default templates.
Don't forget to run `fg init` or set the template path with `fg settings`.

```console
$ fg copy-templates
```
