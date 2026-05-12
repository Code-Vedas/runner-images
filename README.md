# Runner Images

This repository houses container images used by Code Vedas CI/CD pipelines.

Each image lives in its own directory under `images/` so the repository can grow beyond a single runner image.

## Available Images

### `cpp-runner`

Path: `images/cpp-runner`

This image is based on the [C++ Docker image](https://hub.docker.com/_/gcc) and adds:
- [CMake](https://cmake.org/)
- [Catch2](https://github.com/catchorg/Catch2)
- [gcovr](https://gcovr.com/en/stable/)

It is intended for CI/CD pipelines for C++ projects.

## Usage

Published images are available on `ghcr.io/code-vedas/<image-name>` and can be used in GitHub Actions workflows like this:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    container:
      image: ghcr.io/code-vedas/cpp-runner:latest
    steps:
```

## Development

To build the C++ runner image locally:

```bash
docker build -t cpp-runner images/cpp-runner
```

### Building with specific versions

The publish workflow fetches the latest releases of CMake and Catch2 for `cpp-runner`. For local builds, you can override versions with build args:

```bash
# Build with specific versions
docker build \
  --build-arg CMAKE_VERSION=v3.29.0 \
  --build-arg CATCH2_VERSION=v3.7.1 \
  -t cpp-runner \
  images/cpp-runner

# Build with explicit default versions
docker build \
  --build-arg CMAKE_VERSION=v4.0.3 \
  --build-arg CATCH2_VERSION=v3.8.1 \
  -t cpp-runner \
  images/cpp-runner
```

## Repository Layout

```text
images/
  cpp-runner/
    Dockerfile
```

The GitHub Actions workflow is structured to publish one or more images from this repository. Add new image directories under `images/` and extend the workflow matrix for each new image.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
