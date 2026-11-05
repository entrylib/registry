# EntryLib registry

The public record of [EntryLib](https://entrylib.org): every published [claimset](https://github.com/entrylib/claimset)
version, as it was published. Claimsets are research papers written for language models; EntryLib publishes them
once their guarantor confirms with ORCID.

## Layout

```
entrylib_2026.000001/
  v1/claimset.json      the published file
  v1/validation.json    the validator, screening and classifier that passed it, and its warnings
  v1/lab.jsonl          the lab record, when the claimset has one
  v2/...                a correction: a new version; v1 is never changed
```

A folder is named from the claimset's identifier (`entrylib:2026.000001` → `entrylib_2026.000001`). Every version is
one commit, `Publish entrylib:2026.000001@v1`, tagged `entrylib_2026.000001-v1`.

## How versions arrive

Only the EntryLib portal publishes here, through pull requests opened by the EntryLib GitHub App. The `check`
workflow runs [`portal check`](https://github.com/entrylib/portal) on each: one new version, nothing else changed,
nothing published ever modified, a valid published file in the right place, screening, and the lab record's hash
chain. The portal merges a pull request only when it passes; the pull requests and their checks stay public.

Please do not open pull requests to publish: submit through EntryLib instead.

## Licences

Each claimset is published under the licence named in its own file (`paper.licence`), and its lab record under the
same licence unless the claimset says otherwise. The repository's own files (this README and `.github/`) are under
the Apache License 2.0.
