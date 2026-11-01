# Patched build of lowlighter/metrics used by .github/workflows/metrics.yml
#
# Upstream is unmaintained (last commit Dec 2023) and two plugins broke after
# GitHub API changes:
#   - achievements: queried Projects (classic), which GitHub sunset
#   - habits/activity: PushEvent payloads may omit `commits`
#
# This image layers the fix from lowlighter/metrics#1834 (see
# lowlighter-metrics-1834.patch) on top of the official pre-built image, so no
# Chrome/Deno/Ruby/node_modules rebuild is needed. The workflow tags it
# `metrics:3.35.0-beta`, which is the name the action derives from its
# package.json when `use_prebuilt_image: no`, so the action runs this image
# instead of building its own.
FROM ghcr.io/lowlighter/metrics:v3.35-beta@sha256:0a24a23b769873639e7d7d3bebce0aade41ded920f8bfd74650328f4c4967b48

COPY source/plugins/achievements/queries/achievements.graphql /metrics/source/plugins/achievements/queries/achievements.graphql
COPY source/plugins/achievements/list/users.mjs               /metrics/source/plugins/achievements/list/users.mjs
COPY source/plugins/activity/index.mjs                        /metrics/source/plugins/activity/index.mjs
COPY source/plugins/habits/index.mjs                          /metrics/source/plugins/habits/index.mjs

# Dark-mode styling for the classic template (loaded at process start).
COPY dark.css /tmp/dark.css
RUN cat /tmp/dark.css >> /metrics/source/templates/classic/style.css && rm /tmp/dark.css

ENV PUPPETEER_SKIP_CHROMIUM_DOWNLOAD true
ENV PUPPETEER_BROWSER_PATH "google-chrome-stable"

ENTRYPOINT node /metrics/source/app/action/index.mjs
