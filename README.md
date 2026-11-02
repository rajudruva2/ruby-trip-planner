# Trip Planner API

{
  "description": "Trip Planner API is a small Ruby/Sinatra JSON API for DevOps practice."
}

## Features
- Health endpoint: `GET /health`
- List and search records: `GET /trips` or `GET /trips?q=term`
- Get one record: `GET /trips/:id`
- Create a record: `POST /trips`
- Delete a record: `DELETE /trips/:id`
- Dockerfile and GitHub Actions CI workflow

Data is stored in memory for demo simplicity and resets when the process restarts. Do not use this demo storage pattern for production data.

## Run locally
Requires Ruby 3.3+ and Bundler.
```bash
bundle install
bundle exec ruby app.rb
```

Try:
```bash
curl http://localhost:4570/health
curl http://localhost:4570/trips
curl -X POST http://localhost:4570/trips \
  -H 'Content-Type: application/json' \
  -d '{"destination":"Mysuru","days":2,"status":"idea"}'
```

## Run with Docker
```bash
docker build -t ruby-trip-planner .
docker run --rm -p 4570:4570 ruby-trip-planner
```

## CI pipeline
GitHub Actions runs Ruby syntax checks, Minitest smoke tests, and a Docker image build on pushes and pull requests to `main`.

## DevOps practice
Use this repo to practise CI, Docker builds, image tagging, registry publishing, deployment to EC2/Kubernetes, environment variables, approvals, health checks, and rollback.
