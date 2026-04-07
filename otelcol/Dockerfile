# https://developers.home-assistant.io/docs/apps/configuration#app-dockerfile
ARG BUILD_FROM=ghcr.io/home-assistant/base:3.23

FROM otel/opentelemetry-collector-contrib AS otelcol-contrib

FROM ${BUILD_FROM}

COPY --from=otelcol-contrib /otelcol-contrib /usr/bin/otelcol-contrib

# Copy root filesystem
COPY rootfs /
