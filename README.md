# evm-ingestorrr
ingest feeds from evm providers


### Requirements
- [ ] ingests wss from infura/quicknode/alchemy
	- [ ] resilience and fault tolerance built-in
- [ ] forwarded to message queue/pub-sub
- [ ] handlers to index inside microservice
- [ ] gRPC querying of index from microservice
- [ ] api for svelte front end
- [ ] all orchestrated by kubernetes.
- [ ] can be run locally

### Design
* wss microservice
	* ingests for each provider and chain
	* easily configurable with environment secrets well secured
	* message queue/pub-sub config
* indexing microservice
	* feeds off mq/pubsub
	* indexes data to postgresdb
	* gRPC api
* web app microservice
	* hosts app
	* wallet auth
* bonus: uses txhash decoder to better explain transactions for watched addresses


### Use case
* watch an address's activity
* watch a contract's activity
* watch any sort of large trade/transfer of eth
* execute an on-chain transaction based on some activity