# https://developers.home-assistant.io/docs/apps/configuration#app-dockerfile
ARG BUILD_FROM=ghcr.io/home-assistant/base:3.24@sha256:94ff231402a5e7ad2a82e261ad5fa4ffae7d7bb095c3febb2edbdf309c9b6aca

FROM otel/opentelemetry-collector-contrib AS otelcol-contrib

FROM ${BUILD_FROM}

COPY --from=otelcol-contrib /otelcol-contrib /usr/bin/otelcol-contrib

# Copy root filesystem
COPY rootfs /
