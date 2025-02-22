# foundryvtt-cli
The official Foundry VTT CLI

## Installation
```bash
npm install -g @foundryvtt/foundryvtt-cli
```

## Usage
### Help
```bash
fvtt --help
```

### Current CLI Version
```bash
fvtt --version
```

### Configuration
```bash
fvtt configure
```
Determines if your configuration is correct and if not, prompts you to fix it.

#### View
```bash
fvtt configure view
```

View your current configuration.


#### Set
```bash
fvtt configure set "key" "value"
```

Set a configuration value.

#### Get
```bash
fvtt configure get "key"
```

Get a configuration value.

#### Path
```bash
fvtt configure path
```
Outputs the path to your configuration file.

### Launch

```bash
fvtt launch
```
Launches Foundry VTT. Available options are:
* `--demo` - Launches Foundry VTT in demo mode.
* `--port 30000` - Launches Foundry VTT on a specific port.
* `--world my-world` - Launches Foundry VTT straight into a specific world.
* `--noupnp` - Disable UPnP port forwarding.
* `--noupdate` - Disable automatic update checking.
* `--adminKey "ABC123"` - The admin key to secure Foundry VTT's Setup screen with.

### Package

```bash
fvtt package
```
Output the current working package, if any.

#### Workon
```bash
fvtt package workon "1001-fish" --type "Module"
```
Swaps to working on a specific package, eliminating the need to pass `--type` and `--id` to other package commands.

#### Clear
```bash
fvtt package clear
```
Clears the current working package.

#### Unpack
```bash
fvtt package unpack "compendiumName"
```
Reads a database from the current Package /packs/ directory and writes each document as a serialized Object to its own file.
There are a number of options available to customize the output, check out `fvtt package unpack --help` for more information.

#### Pack
```bash
fvtt package pack "compendiumName"
```

Reads a directory of serialized Objects and writes them to a database in the current Package /packs/ directory. There are a number of options available to customize the operation, check out `fvtt package pack --help` for more information.

## Example Workflow

```bash
fvtt configure
fvtt package workon "1001-fish"
fvtt package unpack "fish"
. . . // Make some updates to the files
fvtt package pack "fish"
```

## Development
```bash
git clone
cd foundryvtt-cli
npm install
npm run build
npm link
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
