# Fedora-Update-Enhancer AGENTS

## What This Repo Does

This repo contains `elegant-updater.sh`, a high-impact unattended Fedora updater built around `dnf5`, adaptive parallelism, mirror handling, and cleanup steps. On this machine the canonical invocation is often `sudo update`, but the repo file is `elegant-updater.sh`.

## Main Entrypoints

- `elegant-updater.sh`: the project.
- `README.md`: supported usage, tunables, and validation notes.

## Commands

- `bash -n elegant-updater.sh`
- `shellcheck elegant-updater.sh`
- `sudo bash elegant-updater.sh`

## Repo-Specific Constraints

- This script is intentionally unattended; do not add prompts.
- Keep it `dnf5`-first; do not silently degrade to older package-manager behavior.
- Preserve the terminal color guard so non-TTY output stays clean.
- Keep adaptive job calculation and repo fallback logic reviewable.
- Treat changes as host-maintenance changes that can affect the whole system.

## Agent Notes

- Prefer static checks unless the task explicitly requires a real updater run.
- Call out any change that alters repo handling, cleanup behavior, or parallelism logic.
