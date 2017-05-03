NS = sipbmon
VERSION ?= latest
REPO = prometheus
NAME = prometheus

.PHONY: build restart rm run start stop

build:
	docker build -t $(NS)/$(REPO) .

restart: build rm run

rm: stop
	docker rm $(NAME)

run:
	docker run -d --name $(NAME) \
		-v /var/lib/prometheus:/prometheus \
		$(NS)/$(REPO)

start:
	docker start $(NAME)

stop:
	docker stop $(NAME)

default: build
