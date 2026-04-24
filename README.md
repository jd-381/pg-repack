# pg_repack

## Build

Build the `pg_repack` Docker containers

```bash
# Postgres 13
docker build pg-repack/pg_repack_1.4.6_for_pg_13 -t pg-repack-1.4.6

# Postgres 16
docker build pg-repack/pg_repack_1.5.0_for_pg_16 -t pg-repack-1.5.0

# Postgres 17
docker build pg-repack/pg_repack_1.5.1_for_pg_17 -t pg-repack-1.5.1
```

## Run

Run (Postgres 17 example)

```bash
# set Postgres env vars and pass into the container
docker run -it --rm \
  --network host \
  -e PGHOST \
  -e PGUSER \
  -e PGPASSWORD \
  pg-repack-1.5.1 \
  pg_repack -k -e -d my_db -t my_table --dry-run
```

## Updates
Get new builds from https://pgxn.org/dist/pg_repack/