# escape=`

#
# Development-only image for running Next.js in a containerized environment.
# Assumes that the Next.js rendering host source is mounted to c:\app.
#

ARG BASE_IMAGE
FROM ${BASE_IMAGE} as debug

WORKDIR /app

EXPOSE 3000
ENTRYPOINT "npm run start:connected"