_Reference: https://daily.dev/blog/build-a-chat-app-using-grpc-and-reactjs (This is not self-made)_

## Setting up envoy
```
cd ./grpc-chat-react
docker build -t grpc-web-react .
docker run -d --name grpc-web-react -p 8080:8080 -p 9901:9901 grpc-web-react
```
## Installing protoc and protoc-gen-grpc-web
```
brew install protobuf
brew install protoc-gen-grpc-web
```

## Compiling chat.proto
```
protoc -I=. src/chat.proto --js_out=import_style=commonjs,binary:. --grpc-web_out=import_style=commonjs,mode=grpcwebtext:.
```

TODO: How does it all work?
