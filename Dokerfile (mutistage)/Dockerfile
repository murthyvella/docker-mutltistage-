
#Base image
FROM ubuntu as murthy
RUN apt-get update && apt-get install -y golang-go
ENV GO111MODULE=off

COPY . .

RUN CGO_ENABLED=0 go build -o /app .

#MULTISTAGE 
FROM ubuntu:jammy

COPY --from=murthy /app /app

ENTRYPOINT ["/app"]
~                   
