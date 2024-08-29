# Manifest file

The SkyWhack manifest is a TOML file with the name `sw.toml`, placed in the top directory of a project, that describes an optional SkyWhack workspace and a SkyWhack package.

## Examples

### Client application

The SkyWhack manifest for a client side application looks like the following:

```toml
[package]
name = "example"
version = "0.1.0"

[[source]]
path = "src"
include = true

[client-application]
enable = true

[dependencies]
```

### Library

The SkyWhack manifest for a library looks like the following:

```toml
[package]
name = "example.util"
version = "0.1.0"
author = "Me <me@example.com>"
license = "MIT or Apache-2.0"
description = "My utilities"

[[source]]
path = "src"
include = true

[dependencies]
```

### Server application

The SkyWhack manifest for a server side application looks like the following:

```toml
[package]
name = "example"
version = "0.1.0"

[[source]]
path = "src"
include = true

[server-application]
enable = true
executable-name = "example"
main-class = "example.Example"

[dependencies]
```

### Workspace

The SkyWhack manifest for a workspace that consists of multiple packages looks like the following:

```toml
[workspace]
members = [
    "packages/master",
    "packages/chief",
]
```

## Build script

The SkyWhack manifest may link a script that runs before the sources of a SkyWhack package are compiled.

```toml
[[build-script.source]]
path = "build.as"
include = true
```

## JavaScript

The SkyWhack manifest may specify multiple `[[js]]` sections linking a JavaScript file to be loaded right before the ActionScript environment. The `import-declaration` field must provide highly specific aliases to prevent name conflict.

```toml
[[js]]
path = "lib.min.js"
import-declaration = 'import * as lib from "./lib.min.js";'
```