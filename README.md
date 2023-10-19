# podman-postgresql

Installs a `postgresql` podman container as system service.

## Requirements

Basic ansible, no further dependencies or requirements are needed.

## Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `pg_container_image` | 'docker.io/library/postgres:16' | Container image to be used |
| `pg_container_name` | 'postgresql' | Name of the container in podman |
| `pg_service_name` | 'postgresql' | Name of the systemd service |
| `pg_auto_update` | true | Enable podman-auto update label on the container |
| `pg_container_network` | 'podman' | If defined, use this podman network |
| `pg_container_ip` | '' | If defined, use this container IP |
| `pg_data_dir` | '/srv/postgresql' | Location of the data |
| `pg_mem_limit` | '512M' | If defined, limit the container to this amount of memory |
| `pg_auth_method` | 'ident' | Default auth method for postgresql |
| `pg_default_password` | '' | Default superuser password for postgresql |
| `pg_default_user` | '' | Default superuser |

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: podman-postgresql
           vars:
             pg_default_password: 'notsecret'

## License

[`MIT`](LICENSE)

## Author Information

phoenix
