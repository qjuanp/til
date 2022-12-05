[Offical command documentation](https://docs.docker.com/engine/sbom/)

Uses under the hood Syft

Formats supported:
- syft-json
- cyclonedx-xml
- cyclonedx-json
- github-0-json
- spdx-tag-value
- spdx-json
- table text
- See [[sbom/Image SBOM with Syft]]

Example command
```sh
docker sbom <image-name:tag> --format cyclonedx-json --output sbom.json
```

