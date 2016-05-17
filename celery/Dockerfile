FROM google/python

RUN groupadd -r celery && useradd -r -g celery celery

RUN    apt-get update \
	&& apt-get install -y --no-install-recommends mercurial libjpeg-dev libpng-dev libpqxx3-dev ca-certificates libxml2-dev libxslt1-dev \
	&& apt-get clean \
	&& rm -rf /var/cache/apt/*

VOLUME  ["/log", "/env", "/code"]

ADD run.sh /run.sh
ADD run-server.sh /run-server.sh

CMD ["/run.sh"]
