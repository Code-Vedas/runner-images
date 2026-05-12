# Runner Images

This repository houses container images used by Code Vedas CI/CD pipelines.

Each image lives in its own directory under `images/` so the repository can grow beyond a single runner image.

## Available Images

### `cpp-runner-gcc13`

Path: `images/cpp-runner`

### `cpp-runner-gcc14`

Path: `images/cpp-runner`

### `cpp-runner-gcc15`

Path: `images/cpp-runner`

These images are based on the [C++ Docker image](https://hub.docker.com/_/gcc) and add:
- [CMake](https://cmake.org/)
- [Catch2](https://github.com/catchorg/Catch2)
- [gcovr](https://gcovr.com/en/stable/)

They are intended for CI/CD pipelines for C++ projects, published separately for GCC 13, 14, and 15.

## Usage

Published images are available on `ghcr.io/code-vedas/<image-name>` and can be used in GitHub Actions workflows like this:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    container:
      image: ghcr.io/code-vedas/cpp-runner-gcc13:latest
      # or ghcr.io/code-vedas/cpp-runner-gcc14:latest
    steps:
```

## Development

To build one of the C++ runner images locally:

```bash
docker build --build-arg GCC_VERSION=13 -t cpp-runner-gcc13 images/cpp-runner
docker build --build-arg GCC_VERSION=14 -t cpp-runner-gcc14 images/cpp-runner
docker build --build-arg GCC_VERSION=15 -t cpp-runner-gcc15 images/cpp-runner
```

### Building with specific versions

The publish workflow fetches the latest releases of CMake and Catch2 for all three GCC variants. For local builds, you can override versions with build args:

```bash
# Build with specific versions
docker build \
  --build-arg GCC_VERSION=13 \
  --build-arg CMAKE_VERSION=v3.29.0 \
  --build-arg CATCH2_VERSION=v3.7.1 \
  -t cpp-runner-gcc13 \
  images/cpp-runner

# Build with explicit default versions
docker build \
  --build-arg GCC_VERSION=15 \
  --build-arg CMAKE_VERSION=v4.0.3 \
  --build-arg CATCH2_VERSION=v3.8.1 \
  -t cpp-runner-gcc15 \
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
