# 'make' by itself runs the 'all' target
.DEFAULT_GOAL := all

.PHONY: all
all: lint run

.PHONY: install
install:
	pip install -r requirements.txt

.PHONY: lint
lint:
	find . -name "*.yml" | xargs yamllint -s

.PHONY:
run:
	ansible-playbook build_lab.yml
