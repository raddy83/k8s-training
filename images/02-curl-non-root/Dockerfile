# READ MORE: https://medium.com/better-programming/running-a-container-with-a-non-root-user-e35830d1f42a
FROM alpine:3.12.0

ARG USER_ID=1001
ARG USER=curl

RUN apk add --no-cache curl=7.69.1-r0 \
    && addgroup -g "${USER_ID}" "${USER}" && adduser -D -G "${USER}" -u "${USER_ID}" "${USER}"

USER ${USER_ID}

ENTRYPOINT [ "curl" ]
CMD [ "--version" ]