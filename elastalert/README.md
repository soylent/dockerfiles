### ElastAlert

* Run

  ```sh
  $ docker run \
    --volume $PWD:/etc/elastalert:ro \
    --name elastalert \
    konstantin/elastalert:0.1.21 \
    sh -c "elastalert-create-index --index .elastalert --old-index '' && exec elastalert"
  ```

* Create Elasticsearch Write-back Index

  ```sh
  $ docker run --rm \
    --volume $PWD:/etc/elastalert:ro \
    konstantin/elastalert:0.1.21 \
    elastalert-create-index --index .elastalert --old-index ''
  ```

* Test a Rule

  ```sh
  $ docker run --rm \
    --volume $PWD:/etc/elastalert:ro \
    konstantin/elastalert:0.1.21 \
    elastalert-test-rule rules/example_rule.yaml
  ```

* Build

  ```sh
  docker build . \
    --tag konstantin/elastalert:0.1.21 \
    --build-arg elastalert_version=0.1.21 \
    --build-arg build_date=$(date +%Y-%m-%d)
  ```

#### Configuration

| Name                           | Description               |
|--------------------------------|---------------------------|
| `/etc/elastalert/config.yaml`  | Global configuration file |
| `/etc/elastalert/rules/*.yaml` | Rule configuration files  |
