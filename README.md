# gh-combine-prs

Combines multiple PRs into one.

Usage: 
	
```
gh combine-prs --query "QUERY"
```

Required arguments:
    --query "QUERY"
            sets the query used to find combinable PRs.
            e.g. --query "author:app/dependabot"
            to combine Dependabot PRs

Optional arguments:
    --limit LIMIT
            sets the maximum number of PRs that will be combined.
            Defaults to 50