FROM golang AS buildando

WORKDIR /app
ADD . /app
RUN go build -o go

FROM alpine

WORKDIR /tribix
COPY --from=buildando /app/go  /tribix/

ENTRYPOINT ./go

