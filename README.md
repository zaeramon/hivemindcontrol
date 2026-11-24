# Hive Mind Control Centre — Public Frontend

This repository contains only the static browser frontend for the Hive Mind Control Centre.

- Public site: https://zaeramon.github.io/hivemindcontrol/
- Private source of truth: https://github.com/zaeramon/hive-mind
- Backend: Supabase project `ulbkkjgbmvjxqbqurtux`

## Security boundary

The browser uses only the Supabase publishable key. It never contains the service-role key.
All dashboard data and privileged actions are served by the Supabase Edge Function, which validates the bearer token against Supabase Auth and requires trusted `app_metadata.hive_role = super_admin`. Creating an account does not grant administrator access.

This public repository must contain frontend assets only. Do not add private repository files, credentials, service-role keys, agent tokens, local launchers, or internal project data.

The private Windows launcher, GitHub checkpoint sync, and self-updater remain in the private repository and are not part of this static Pages build.

## Deployment

GitHub Pages is deployed from the `main` branch by the GitHub Actions workflow in `.github/workflows/deploy-pages.yml`. Every frontend commit triggers a fresh static-site deployment.
