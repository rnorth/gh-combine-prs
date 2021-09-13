# gh-combine-prs

Combines multiple PRs into one. 
Intended for use in repositories that receive many PRs that can be merged simultaneously, e.g. trivial Dependabot version bump PRs.

The tool will attempt to create one PR that contains all PRs that:

* match a provided query - e.g. `--query "author:app/dependabot"` so that only Dependabot PRs are processed
* and have checks passing
* and that can be merged cleanly - e.g. if two combinable PRs conflict with one another, only one will be merged.

This tool does not automerge into the `master`/`main` branch - it just attempts to create one unified PR for review and automated checks to run against.

When merging the combined PR, is recommended that a Merge Commit be created. 
This allows GitHub to automatically detect that all of the original combined PRs have been merged, so that their state can be set correctly.

## Installation

```
gh extension install rnorth/gh-combine-prs
```

## Usage
	
```
gh combine-prs --query "QUERY"
```

### Required arguments
    --query "QUERY"
            sets the query used to find combinable PRs.
            e.g. --query "author:app/dependabot"
            to combine Dependabot PRs

### Optional arguments
    --limit LIMIT
            sets the maximum number of PRs that will be combined.
            Defaults to 50

## License

See [LICENSE](./LICENSE)