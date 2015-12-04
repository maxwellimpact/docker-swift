A baseline Docker image for Swift on Ubuntu 15.10. Open to suggestions.
 
 
```
from swiftlang/base

RUN apt-get install -y git

RUN git clone https://github.com/apple/example-package-dealer.git
WORKDIR /example-package-dealer
RUN swift build

RUN .build/debug/Dealer
```