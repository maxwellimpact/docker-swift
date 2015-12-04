from ubuntu:15.10

RUN apt-get -y update

RUN apt-get install -y \
  wget \
  rsync \
  clang \
  libicu-dev
  
ENV SWIFT_VERSION 2.2-SNAPSHOT-2015-12-01-b
ENV SWIFT_PLATFORM ubuntu15.10
  
RUN wget -q -O - https://swift.org/keys/all-keys.asc | gpg --import -

RUN wget https://swift.org/builds/ubuntu1510/swift-$SWIFT_VERSION/swift-$SWIFT_VERSION-$SWIFT_PLATFORM.tar.gz
RUN wget https://swift.org/builds/ubuntu1510/swift-$SWIFT_VERSION/swift-$SWIFT_VERSION-$SWIFT_PLATFORM.tar.gz.sig

RUN gpg --keyserver hkp://pool.sks-keyservers.net --refresh-keys Swift
RUN gpg --verify swift-$SWIFT_VERSION-$SWIFT_PLATFORM.tar.gz.sig

RUN tar xzf swift-$SWIFT_VERSION-$SWIFT_PLATFORM.tar.gz

RUN rm swift-$SWIFT_VERSION-$SWIFT_PLATFORM.tar.gz
RUN rm swift-$SWIFT_VERSION-$SWIFT_PLATFORM.tar.gz.sig

RUN rsync -a -v --ignore-existing swift-$SWIFT_VERSION-$SWIFT_PLATFORM/usr/ /usr

RUN rm -rf swift-$SWIFT_VERSION-$SWIFT_PLATFORM