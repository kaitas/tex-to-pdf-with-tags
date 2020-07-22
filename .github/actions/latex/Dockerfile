FROM ubuntu:18.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
  && apt-get install -y --no-install-recommends \
    curl \
    latexmk \
    lmodern \
    texlive \
    texlive-latex-extra \
    texlive-lang-japanese \
  && rm -rf /var/lib/apt/lists/*

RUN apt-get update \
  && apt-get install -y tzdata
  
RUN mktexlsr && mkdir -p /app
WORKDIR /app

ADD entrypoint.sh /entrypoint.sh
RUN ["chmod", "+x", "/entrypoint.sh"]
ENTRYPOINT ["/entrypoint.sh"]
