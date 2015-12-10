A Docker image for Swift on Ubuntu. Tried to install as little as possible onto the base Ubuntu image. Open to suggestions and pull requests.
 
Here's an example Dockerfile for building the Dealer sample project from Apple:
 
```
from dockerswift/swift

RUN git clone https://github.com/apple/example-package-dealer.git
WORKDIR /example-package-dealer
RUN swift build

CMD [".build/debug/Dealer"]
```
