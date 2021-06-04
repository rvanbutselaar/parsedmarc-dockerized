# :e-mail: parsedmarc-dockerized

## :information_source: Info

This stack includes:

- [ParseDMARC](https://domainaware.github.io/parsedmarc/) image to analizing reports (builded from Dockerfile, use pypy image)
- [Elasticsearch & Kibana](https://www.elastic.co/guide/index.html) to store and visualize parsed data
- [Nginx](https://docs.nginx.com/) to handle basic authorization and SSL offloading

## How-to deploy

First of all you need to have :whale: Docker and :octocat: Docker Compose.

1. Start stack.

```bash
docker-compose -up d
```

1. Import Kibana Saved Objects

Go to [http://localhost:5601/app/management/kibana/objects] click on `Import`.

Import `kibana/export.ndjson` with override.

1. Copy DMARC reports from mailbox to: `dmarc-reports`. The following file extensions are supported: `.xml, .zip, .xml.gz`

1. Open the dashboard to get an overview of the failed DMARC reports [http://localhost:5601/app/dashboards#/view/269ba470-2871-11e8-b8b2-15742da3055c]
