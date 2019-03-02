# 'make' by itself runs the 'all' target
.DEFAULT_GOAL := all

.PHONY: all
all: lint unit run

.PHONY: lint
lint:
	@echo "Starting  lint"
	find . -name "*.yml" | xargs ansible-lint
	find . -name "*.py" | xargs pylint
	find . -name "*.py" | xargs bandit
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
