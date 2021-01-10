# Hardhat Docgen

Generate NatSpec documentation automatically on compilation with Hardhat.

## Installation

```bash
yarn add --dev hardhat-docgen
```

## Usage

Load plugin in Hardhat config:

```javascript
require('hardhat-docgen');
```

Add configuration under the `docgen` key:

| option | description | default |
|-|-|-|
| `path` | path to HTML export directory (relative to Hardhat root) | `'./docgen'`
| `clear` | whether to delete old files in `path` on  | `false` |
| `runOnCompile` | whether to automatically generate documentation during compilation | `false` |

```javascript
docgen: {
  path: './docs',
  clear: true,
  runOnCompile: true,
}
```

The `path` directory will be created if it does not exist.

The `clear` option is set to `false` by default because it represents a destructive action, but should be set to `true` in most cases.

The included Hardhat task may be run manually; however, it is imperative that the `compile` task be run at least once after plugin installation to ensure that the correct compiler options are set:

```bash
yarn run hardhat docgen
```
