FROM quay.io/operator-framework/helm-operator:v1.34

ADD LICENSE /licenses/LICENSE

LABEL name="kong-operator" \
      maintainer="harry@konghq.com" \
      vendor="Kong Inc" \
      version="v0.9.0" \
      summary="kong-operator installs and manages Kong in your k8s environemnt" \
      description="kong-operator installs and manages Kong in your k8s environemnt"

COPY watches.yaml ${HOME}/watches.yaml
COPY helm-charts/ ${HOME}/helm-charts/
