# Build stage 
FROM golang:1.18 AS builder
# set the working directory
WORKDIR /app

# copy go.mod and go.sum to download dependencies
COPY go.mod ./
COPY go.sum ./
RUN go mod download

# copy the rest of the file to the docker image 
COPY . ./

# Build the Application
RUN go build -o /main

# final stage 
FROM alpine:latest

# set the final working directory
WORKDIR /

# copy the executable file from the build stage 
COPY --from=builder /main /main

# Expose port 8000 for communication
EXPOSE 8000

# Default command to run 
CMD ["/main"]
