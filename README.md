# Default branches Exploration

The goal of this sample repo (project on CircleCI) is to test the behaviours of the following features for [default branches](https://support.circleci.com/hc/en-us/articles/15222074173723-How-to-allowlist-additional-branches-for-Only-Build-Pull-Requests):

- Auto-cancel redundant workflows ON
- Only build PRs ON

## Current default branches:

```console
$ curl -s -X GET \
  -H "Circle-Token: $CIRCLE_TOKEN" \
  -H "Accept: application/json" \
  -H "Content-Type: application/json" \
  https://circleci.com/api/v1.1/project/github/kelvintaywl-cci/default-branches-explore/settings | jq '.feature_flags."pr-only-branch-overrides"'

[
  "edge[0-9]*",
  "main"
]
```

NOTE: this will be a PR from my-first-pr (not a default branch) onto edge100 (default branch)
