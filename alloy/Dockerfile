# https://developers.home-assistant.io/docs/apps/configuration#app-dockerfile
ARG BUILD_FROM=ghcr.io/home-assistant/base:3.24

FROM grafana/alloy:v1.18.1 AS alloy

FROM ${BUILD_FROM}

RUN apk add --no-cache gcompat

COPY --from=alloy /bin/alloy /usr/bin/alloy

# Copy root filesystem
COPY rootfs /
