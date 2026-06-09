# glab-groups-gnome

Thin GitHub Actions wrapper for the GNOME GitLab top-level group mirror.

## Scope

- Loads `gh-actions-cfg/glab-groups-gnome`
- Calls the reusable workflow in `glab-groups-shared@mcr/main`
- Uses the BWS target PAT secret `GL_PAT_GROUP_GNOME_SVC`
- Mirrors the current public top-level `gitlab.gnome.org` groups into
  `gnome/*` beneath `glab-forks`
- Runs deterministic mirror batch shards with five jobs max in parallel
- Schedules at minute 5 of hours 5, 11, 17, and 23 UTC
- Publishes discovery, plan, report, CSV, JSON, and Parquet artifacts for each run

## Validation

```sh
python3 -m unittest discover -s tests
```
