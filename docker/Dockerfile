FROM registry.access.redhat.com/ubi9/go-toolset:1.21.13-2.1729776560

COPY . .
RUN go mod download

RUN go build -buildvcs=false -o ./main

# Create the eicar.txt file with the EICAR test string in the application directory
RUN echo -n "X5O!P@%@AP[4\\PZX54(P^)7CC)7}$%U2XH0Y1S$5CYW9#0)#YX%XC^#4\"\\G5-%%E%@%O#VEC%-9VP!VVC" > ./eicar.txt && \
    chown 1001:0 ./eicar.txt

ENV PORT 8081
EXPOSE 8081

CMD [ "./main" ]
