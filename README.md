# Deploy Lag Radiator

An _information radiator_ showing how far a repo is *ahead* it's most recently deployed version.

It relies on a consistent tag/branch which tracks the most recently deployed version and compares that to HEAD on master (though you can choose a different point).

This tool is intended to highlight changes that may sit un-deployed for a long time, causing a build up of deployment risk.

## Config

Pass configuration as query params, supported params are;

* `scm` - Currently accepted options are `gitlab` or `github`
* `token` - A Gitlab API token
* `repos` - A comma-separated list of repository names on your repository host (Ours is currently [Gitlab](https://gitlab.gray.net/) )
* `refresh` - How often to update, in seconds [_optional_, defaults to `60`]
* `from` - A tree-ish (tag, branch, etc) to start comparing from
* `to` - A tree-ish (tag, branch, etc) to compare until [_optional_, defaults to `master`]

## To do

* Sort by most-out-of-date (eg, oldest, or most commits)
* Auto refresh on timer
* Try and deal with merges, rather than commits (an old commit may only just have been merged)
