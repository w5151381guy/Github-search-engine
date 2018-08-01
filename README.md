# Github-search-engine

## Development

### Prerequisite

- [docker](https://docs.docker.com/install/#supported-platforms) >= 17
- [docker-compose](https://docs.docker.com/compose/install/#install-compose)
- [node](https://nodejs.org/en/) >= 8
- [curl](https://curl.haxx.se/download.html)

### Setup Develop Environment

- run Elastic Search in background

```bash
docker-compose -f docker-compose-dev.yml up -d
```

### CRUD using curl

1.  create a user Larry, id = `IDIDID`

```bash
curl -X POST 'localhost:9200/recommend/user/IDIDIDID?pretty' -H 'Content-Type: application/json' -d '{"name": "Larry", "birth": "850806"}'
```

2.  search users whose name contain `Larry`

```bash
curl -X GET 'localhost:9200/recommend/_search?pretty&q=name:Larry'
```

3.  update name to `Larry Lu`

```bash
curl -X POST 'localhost:9200/recommend/user/IDIDIDID/_update?pretty' -H 'Content-Type: application/json' -d '{"doc": {"name": "Larry Lu"}}'
```

4.  delete user

```bash
curl -X DELETE 'localhost:9200/recommend/user/IDIDIDID?pretty'
```

---

## Deployment
