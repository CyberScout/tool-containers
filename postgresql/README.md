<img src="https://www.postgresql.org/media/img/about/press/elephant.png" alt="PostgreSQL logo" width="128">

PostgreSQL Server
=================

This set of scripts launches PostgreSQL Server within a Docker container. Two versions are currently supported -- 10 and 11.

Building a custom script
------------------------

The functions that launch the container are contained in `base`. This file can also be sourced in a custom script, along with variable overrides to alter the functionality.

### Variables

The following variables are available:

| Variable          | Purpose                                                                                                                 | Required or Default                  |
|-------------------|-------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
| `major_version`   | The major version of PostgreSQL to launch. Other variables will use this value to build defaults                        | **Required**                         |
| `password_file`   | The file that contains the password for the `postgres` user                                                             | `.postgres_password`                 |
| `volume_name`     | The name of the Docker volume to mount as the PostgreSQL data directory                                                 | `postgres_data`                      |
| `container_name`  | The name of the Docker container                                                                                        | `postgresql_server_${major_version}` |
| `image_name`      | The image to use as the base of the container                                                                           | `postgres:${major_version}-alpine`   |
| `pgdata_location` | The directory inside the container to store the data. This will be a directory relative to `/var/lib/postgresql/data/`. | `pg-${major_version}`                |
| `local_port`      | The network port on `localhost` that Docker will forward to port `5432` on the container                                | `${major_version}032`                |
