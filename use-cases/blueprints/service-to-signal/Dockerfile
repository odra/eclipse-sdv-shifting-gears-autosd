FROM quay.io/centos/centos:stream10 AS builder

RUN dnf install -y git

RUN git clone --recurse-submodules https://github.com/eclipse-sdv-blueprints/service-to-signal.git /tmp/service-to-signal

FROM ghcr.io/eclipse-autosd/eclipse-autosd-bootc-qemu:latest

COPY files/ /

COPY --from=builder /tmp/service-to-signal /usr/share/esdv/service-to-signal
