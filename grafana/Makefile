NS = sipbmon
VERSION ?= latest
REPO = grafana
NAME = grafana
INSTANCE = 0

.PHONY: build restart rm run start stop

build:
	docker build -t $(NS)/$(REPO) .

restart: build rm run

rm: stop
	docker rm $(NAME)

run:
	docker run -d --name $(NAME) \
		-v /var/lib/grafana:/var/lib/grafana \
		-p 3000:3000 \
		$(NS)/$(REPO)

start:
	docker start $(NAME)

stop:
	docker stop $(NAME)

default: build
