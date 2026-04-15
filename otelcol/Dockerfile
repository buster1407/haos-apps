# https://developers.home-assistant.io/docs/apps/configuration#app-dockerfile
ARG BUILD_FROM=ghcr.io/home-assistant/base:3.23@sha256:5ea71eca9735949b080a05d271988c9663af3bd1050297abedefa222c61e6807

FROM otel/opentelemetry-collector-contrib@sha256:a516c26968aa1feb5e5fc0562e3338ea13755cb4f373603226bcc4e276374ad0 AS otelcol-contrib

FROM ${BUILD_FROM}

COPY --from=otelcol-contrib /otelcol-contrib /usr/bin/otelcol-contrib

# Copy root filesystem
COPY rootfs /
