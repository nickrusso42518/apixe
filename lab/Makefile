# 'make' by itself runs the 'all' target
.DEFAULT_GOAL := all

.PHONY: all
all: lint run

.PHONY: lint
lint:
	find . -name "*.yml" | xargs yamllint -s

.PHONY:
run:
	ansible-playbook build_lab.yml
