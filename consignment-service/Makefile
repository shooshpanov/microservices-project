build:
	protoc -I. --go_out=plugins=micro:$(GOPATH)/src/github.com/shooshpanov/microservices-project/consignment-service/proto/consignment/consignment.proto
		
	docker build -t consignment-service .

run:
		docker run -d --net="host" -p 50052 -e MICRO_SERVER_ADDRESS=:50052 -e MICRO_REGISTRY=mdns -e DISABLE_AUTH=true consignment-service

		docker run -d -p 5432:5432 postgres