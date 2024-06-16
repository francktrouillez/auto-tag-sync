# Auto-Tag Sync

This action will automatically sync major and minor tags with the latest release tag.

## Inputs

### `github_token`
**required** The GitHub token to use to create the tags.
### `version_prefix`
**optional**(default: `'v'`) The prefix to use for the version tags.
### `version_suffix`
**optional**(default: `''`) The suffix to use for the version tags.
### `version_separator`
**optional**(default: `'.'`) The separator to use for the version tags.

## Example usage

```yaml
name: Tag sync
on:
  release:
    types: [published]

jobs:
  tag-sync:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout
      uses: actions/checkout@v4
    - name: Tag sync
      uses: francktrouillez/auto-tag-sync@v1
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
```

## Troubleshooting

If you are having permission issues, make sure the [action has the permission to write in the repository](https://docs.github.com/en/actions/using-jobs/assigning-permissions-to-jobs).

## Contributions

Contributions are welcome! Feel free to open an issue or submit a pull request if you have any ideas or improvements for the action.
