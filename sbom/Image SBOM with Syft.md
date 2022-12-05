Example commands

```sh
syft johscheuer/todo-app-web --scope all-layers -o cyclonedx-json > johscheuer-todo-app-web.json
syft nginx --scope all-layers -o cyclonedx-json > nginx.json
syft postgres --scope all-layers -o cyclonedx-json > postgres.json
syft qjuanp/t-multi-client-latest --scope all-layers -o cyclonedx-json > j qjuanp-t-multi-client-latest.json
```