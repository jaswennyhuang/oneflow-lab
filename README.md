# oneflow-lab (platform repo, Lab 1)

Holds which version of each service runs in each environment.

- `environments/dev/<service>.yaml`: written by the service's build on every merge. A change here deploys **dev**.
- `environments/staging/<service>.yaml`: written on the open `release/*` branch when a service tags a release. A change there deploys **staging**.
- `start-release`: run it by hand to cut `release/<date>` from `main`. Only one release can be open.
- `environments/prod/<service>.yaml`: filled by `prepare-prod` inside the platform release PR (copied from staging).
- `release.yml`: on a `release/*` branch, release-please opens the platform release PR. Merging it tags `vX.Y.Z`.
- `deploy-prod.yml`: a new `vX.Y.Z` tag deploys **prod** after approval.
