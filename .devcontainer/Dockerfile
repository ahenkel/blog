FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

# Hugo 0.170+ compiles the theme's SCSS with Dart Sass, which must be on PATH as `sass`.
# Keep in sync with DART_SASS_VERSION in .github/workflows/hugo.yml
ARG DART_SASS_VERSION=1.108.2
RUN arch="$(dpkg --print-architecture)" \
    && case "$arch" in amd64) arch=x64 ;; arm64) arch=arm64 ;; *) echo "Unsupported architecture: $arch" >&2; exit 1 ;; esac \
    && curl -fsSL "https://github.com/sass/dart-sass/releases/download/${DART_SASS_VERSION}/dart-sass-${DART_SASS_VERSION}-linux-${arch}.tar.gz" \
       | tar -xz -C /usr/local \
    && ln -s /usr/local/dart-sass/sass /usr/local/bin/sass \
    && sass --version
