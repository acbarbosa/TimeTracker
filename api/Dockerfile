FROM haskell:8.0.2

ADD TimeTrackerApi.cabal /opt/TimeTrackerApi/
ADD src /opt/TimeTrackerApi/src

WORKDIR /opt/TimeTrackerApi

RUN cabal update && cabal install snap
RUN cabal install --bindir=/usr/local/bin

RUN useradd -m ttapi
USER ttapi

CMD /usr/local/bin/TimeTrackerApi -p $PORT
