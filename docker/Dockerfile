FROM registry.access.redhat.com/ubi9/go-toolset:1.21.13-2.1729776560

COPY . .
RUN go mod download

RUN go build -buildvcs=false -o ./main

# Copy the EICAR test file into the container
COPY eicar.txt /eicar.txt

ENV PORT 8081
EXPOSE 8081

CMD [ "./main" ]
