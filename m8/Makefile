# 'make' by itself runs the 'all' target
.DEFAULT_GOAL := all

.PHONY: all
all: lint unit run

.PHONY: install
install:
	pip install -r requirements.txt

.PHONY: lint
lint:
	@echo "Starting  lint"
	find . -name "*.yml" | xargs yamllint -s
	find . -name "*.py" | xargs pylint
	find . -name "*.py" | xargs bandit
	ansible-lint full_iac.yml
	@echo "Completed lint"

.PHONY:
unit:
	@echo "Starting  unit tests"
	ansible-playbook tests/unittest.yml
	@echo "Completed unit tests"

.PHONY:
run:
	@echo "Starting  live playbook run"
	ansible-playbook full_iac.yml
	@echo "Completed live playbook run"
