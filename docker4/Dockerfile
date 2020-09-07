FROM golang

WORKDIR /app
ADD . /app
RUN go build -o helloworld
ENTRYPOINT ./helloworld

