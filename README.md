# amiberry-docker-fedora-x86_64

A Dockerfile which creates an image with all requirements to build Amiberry for a Fedora `x86_64` platform.

The image is based on Fedora 44 by default and includes all Amiberry dependencies, including SDL3 and SDL3_image. Override `fedora_release` at build time when moving release CI to a newer Fedora base.

The full image is available on DockerHub: <https://hub.docker.com/repository/docker/midwan/amiberry-fedora-x86_64>

## Usage

```bash
docker run --rm -it -v <dir-you-cloned-amiberry-into>:/build midwan/amiberry-fedora-x86_64:latest
```

Then you can proceed to compile Amiberry as usual, e.g.:

```bash
cmake -B build && cmake --build build
```

## Building the image locally

To build the image yourself:

```bash
docker build -t amiberry-fedora-x86_64:latest .
```

## CI/CD

Images are automatically built and pushed to DockerHub via GitHub Actions on every push to `main` and on a daily schedule.
