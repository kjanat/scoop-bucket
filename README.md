# scoop-bucket

[![CI](https://github.com/kjanat/scoop-bucket/actions/workflows/ci.yaml/badge.svg)](https://github.com/kjanat/scoop-bucket/actions/workflows/ci.yaml)

[Scoop](https://scoop.sh) bucket for kjanat's tools: actionlint, runner, svg and more.

```powershell
scoop bucket add kjanat https://github.com/kjanat/scoop-bucket
scoop install kjanat/actionlint
```

## Packages

| Package                    | Description                                                                   |
| -------------------------- | ----------------------------------------------------------------------------- |
| [`actionlint`][actionlint] | Static checker for GitHub Actions workflow files, with ShellCheck integration |

Others follow as their releases start publishing here.

`scoop install actionlint` without the bucket prefix resolves to the `actionlint` in
Scoop's main bucket, which is the upstream project. Use `kjanat/actionlint` for this
fork.

## Tab completion

PowerShell loads completions from your profile. Add one line to `$PROFILE`:

```powershell
actionlint -completion powershell | Out-String | Invoke-Expression
```

## How manifests get here

Each release pipeline writes its manifest with [GoReleaser][goreleaser] and commits it
to this repository, so manifests track releases without a checkver or autoupdate step.
Edits by hand are overwritten on the next release; fix the project's `.goreleaser.yaml`
instead.

CI runs Scoop's own bucket tests on every push: schema validation for each manifest,
plus the file checks Scoop expects of a bucket.

## License

[MIT](LICENSE). Each package carries its own license, named in its manifest.

[actionlint]: https://github.com/kjanat/actionlint
[goreleaser]: https://goreleaser.com/customization/scoop/
