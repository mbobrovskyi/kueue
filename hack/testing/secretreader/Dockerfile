FROM golang:1.27-alpine@sha256:f92b6ef800e499660581efdabdf25d9d817a9d124eaf900924f0504e7e27e12d AS builder
ARG PLUGIN_VERSION
RUN go install sigs.k8s.io/cluster-inventory-api/plugins/secretreader/cmd/plugin@${PLUGIN_VERSION}

# Final image
FROM alpine:3.24.3@sha256:be2656061b536c1883c4034790e21d0a09c5aaaf51968b89368a3c0371ea2c9a
USER 65534:65534
# Place the binary at /bin to mirror the official secretreader image layout, so the
# init-container fallback and the image-volume mount expose it at the same path.
COPY --from=builder /go/bin/plugin /bin/secretreader-plugin
