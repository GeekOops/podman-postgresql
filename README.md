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
| `pg_mem_limit` | '' | If defined, limit the container to this amount of memory |
| `pg_auth_method` | 'ident' | Default auth method for postgresql |
| `pg_default_password` | '' | Default superuser password for postgresql |
| `pg_default_user` | '' | Default superuser |

Recommendation: Tag a specific version in `pg_container_image` and don't use `latest`, as major database updates might require manual migration.

## Example Playbook

Minimal working example playbook:

```yaml
- hosts: servers
  roles:
     - role: podman-postgresql
       vars:
         pg_default_password: 'notsecret'
```

Extended example

```yaml
- hosts: servers
  roles:
     - role: podman-postgresql
       vars:
         pg_container_image: 'docker.io/library/postgres:16'
         pg_default_password: 'notsecret'
         pg_mem_limit: '512M'
         pg_container_ip: '10.88.0.101'
         pg_default_user: 'admin'
         
```

## License

[`MIT`](LICENSE)

## Author Information

phoenix
