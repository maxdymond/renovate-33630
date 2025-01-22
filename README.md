# 33630

## Current behavior

When Renovate has multiple Cargo.lock changes (e.g. it has a virtual workspace)
then it loses any changes to Cargo.lock made in a postUpgradeTask.

See example:
  - postUpgradeTask is configured to run

    ```
    sed -i 's@0.1.0@0.1.1@g' member1/Cargo.toml
    cargo check --workspace
    ```

    the result of which is that Cargo.lock is updated with `version 0.1.1` for member1

  - However, the resulting MR does not have this change: https://github.com/maxdymond/renovate-33630/pull/1/files#diff-13ee4b2252c9e516a0547f2891aa2105c3ca71c6d7a1e682c69be97998dfc87eR25

## Expected behavior

postUpgradeTasks can affect files which have multiple entries in `updatedArtifacts`.

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/33630
