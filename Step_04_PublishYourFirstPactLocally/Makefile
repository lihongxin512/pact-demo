.EXPORT_ALL_VARIABLES:
PACT_BROKER_BASE_URL=http://0.0.0.0:8000
PACT_BROKER_USERNAME=pact_workshop
PACT_BROKER_PASSWORD=pact_workshop
PACT_CLI_DOCKER="docker run --rm -v ${PWD}:${PWD} -e PACT_BROKER_BASE_URL -e PACT_BROKER_TOKEN pactfoundation/pact-cli"

doctor:
	./pact_helper.sh doctor

install_pact_cli_ruby:
	./pact_helper.sh install-pact-cli ruby

install_pact_cli_standalone:
	./pact_helper.sh install-pact-cli standalone

install_pact_cli_docker:
	./pact_helper.sh install-pact-cli docker

publish:
	pact-broker publish pacts --consumer-app-version $(shell git rev-parse HEAD) --branch $(shell git rev-parse --abbrev-ref HEAD)

publish_docker:
	"${PACT_CLI_DOCKER}" pact-broker publish ${PWD}/pacts --consumer-app-version $(shell git rev-parse HEAD) --branch $(shell git rev-parse --abbrev-ref HEAD)