## Custom Debs Repository

### How to use

You will need to publish github releases in your deb repositories to serve deb package files to be downloaded from. For example, [ArchieMeng/box64](https://github.com/ArchieMeng/box64)

And then, you need to configure this repository with the following steps:

- Fill package_repos with the HTTP URLs of **github repositories** that serves deb package files you want this repository to include.
- Configure workflow environment variables in [generate.yml](.github/workflows/generate.yml)
  - CODENAME
  - COMPONENTS
  - ARCHITECTURES
- Configure Signing key secret `SIGNING_KEY` in `Repository Settings > Secrets and variables > Actions`
- Check the protection rules in `Repository Settings > Environments > github-pages`. If the allowed deployment branch is not the one you want, it has to be changed to the one for actual deployments.