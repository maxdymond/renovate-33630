# Renovate discussion 33630

## Current behavior

When Renovate has multiple Cargo.lock changes (e.g. it has a virtual workspace)
then it loses any changes to Cargo.lock made in a postUpgradeTask.

## Expected behavior

postUpgradeTasks can affect files which have multiple entries in `updatedArtifacts`.

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/33630
