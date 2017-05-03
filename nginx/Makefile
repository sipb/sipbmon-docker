NS = sipbmon
VERSION ?= latest
REPO = nginx
NAME = nginx

.PHONY: build restart rm run start stop

build:
	docker build -t $(NS)/$(REPO) .

restart: build rm run

rm:
	docker rm $(NAME)

run:
	docker run -d --name $(NAME) \
		--link grafana --link prometheus \
		-v /etc/ssl/private:/etc/ssl/private \
		-p 80:80 -p 443:443 -p 9090:9090 \
		$(NS)/$(REPO)

start:
	docker start $(NAME)

stop:
	docker stop $(NAME)

default: build
