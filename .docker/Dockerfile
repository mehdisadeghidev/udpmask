FROM alpine:3.17 as builder

WORKDIR /src

RUN apk update && \
    apk add git make build-base

COPY . .

RUN make install

FROM alpine:3.17 as runtime

COPY --from=builder /src/udpmask /usr/local/bin

ENTRYPOINT [ "udpmask" ]
