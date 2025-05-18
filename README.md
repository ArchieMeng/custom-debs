## Custom Debs Repository

### How to use

You will need some http sites to serve deb package files to be downloaded from. And their structure should be like:

- https://yourdebpacakgesite
  - files (Contains a list of all the files hosted on the site. See https://archiemeng.github.io/kernel_sony_sm8250/files as an example)
  - package1.deb
  - package2.deb
  - ....

And then, you need to configure this repository with the following steps:

- Fill package_url.list with the HTTP URLs of deb package files you want the repository to include.
- Configure workflow environment variables in [generate.yml](.github/workflows/generate.yml)
  - CODENAME
  - COMPONENTS
  - ARCHITECTURES
- Configure Signing key secret `SIGNING_KEY` in `Repository Settings > Secrets and variables > Actions`
- Check the protection rules in `Repository Settings > Environments > github-pages`. If the allowed deployment branch is not the one you want, it has to be changed to the one for actual deployments.