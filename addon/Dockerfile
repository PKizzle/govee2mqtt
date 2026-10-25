ARG BUILD_FROM=ghcr.io/home-assistant/base-debian:bookworm
ARG GOVEE2MQTT_IMAGE=ghcr.io/wez/govee2mqtt:latest
FROM ${GOVEE2MQTT_IMAGE} AS govee2mqtt
FROM ${BUILD_FROM}
LABEL \
  org.opencontainers.image.title="Home Assistant Add-on: Govee to MQTT Bridge" \
  org.opencontainers.image.description="Acts as a bridge between Govee devices and Home Assistant, via the Home Assistant MQTT Integration." \
  org.opencontainers.image.licenses="MIT"
COPY run.sh /run.sh
COPY --from=govee2mqtt /app/govee /app/
COPY --from=govee2mqtt /app/assets /app/assets/
COPY --from=govee2mqtt /app/AmazonRootCA1.pem /app/
CMD [ "/run.sh" ]
