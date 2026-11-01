# Patched `lowlighter/metrics`

`lowlighter/metrics` is unmaintained and two plugins fail against today's
GitHub API. This directory builds a thin image on top of the official one
with the fix from [lowlighter/metrics#1834](https://github.com/lowlighter/metrics/pull/1834)
applied, plus dark-mode styling for the classic template.

| File | Purpose |
| --- | --- |
| `Dockerfile` | `FROM ghcr.io/lowlighter/metrics:v3.35-beta` + copies the patched files |
| `source/**` | The four patched plugin files (achievements, activity, habits) |
| `lowlighter-metrics-1834.patch` | The upstream PR diff the files were produced from |
| `dark.css` | `prefers-color-scheme: dark` overrides appended to the classic template |

The workflow builds this as `metrics:3.35.0-beta` and runs the official action
with `use_prebuilt_image: no`, which makes the action reuse the local image.
