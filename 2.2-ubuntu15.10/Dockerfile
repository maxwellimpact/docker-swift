from ubuntu:15.10

RUN apt-get -y update && apt-get install -y \
  wget \
  git \
  rsync \
  clang \
  libicu-dev \
  libpython2.7-dev
  
ENV SWIFT_VERSION 2.2-SNAPSHOT-2016-02-08-a
ENV SWIFT_PLATFORM ubuntu15.10
ENV SWIFT_PLATFORM_FOLDER ubuntu1510
  
RUN wget -q -O - https://swift.org/keys/all-keys.asc | gpg --import - \
 && wget https://swift.org/builds/$SWIFT_PLATFORM_FOLDER/swift-$SWIFT_VERSION/swift-$SWIFT_VERSION-$SWIFT_PLATFORM.tar.gz \
 && wget https://swift.org/builds/$SWIFT_PLATFORM_FOLDER/swift-$SWIFT_VERSION/swift-$SWIFT_VERSION-$SWIFT_PLATFORM.tar.gz.sig \
 && gpg --keyserver hkp://pool.sks-keyservers.net --refresh-keys Swift \
 && gpg --verify swift-$SWIFT_VERSION-$SWIFT_PLATFORM.tar.gz.sig \
 && tar xzf swift-$SWIFT_VERSION-$SWIFT_PLATFORM.tar.gz \
 && rm swift-$SWIFT_VERSION-$SWIFT_PLATFORM.tar.gz \
 && rm swift-$SWIFT_VERSION-$SWIFT_PLATFORM.tar.gz.sig \
 && rsync -a -v --ignore-existing swift-$SWIFT_VERSION-$SWIFT_PLATFORM/usr/ /usr \
 && rm -rf swift-$SWIFT_VERSION-$SWIFT_PLATFORM
 
