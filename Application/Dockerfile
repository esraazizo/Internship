# Start with a base image that includes Go installed
FROM golang:1.16.5-alpine3.14

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . .

# Build the Go application
RUN go build -o main .

# Expose port 8080 for the application to run on
EXPOSE 9090

# Run the Go application when the container starts
CMD ["./main"]
