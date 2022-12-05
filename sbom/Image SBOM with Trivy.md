Run command:
```sh
docker run aquasec/trivy image --format
```

Additional scanning information available:
- Security Scann
- Configuration Scan
	- It can be defined policies in REGO to evaluate images
- licenses for packages installed by `apk`, `apt-get`, `dnf`, `npm`, `pip`, `gem`
- Complience records
- Has Experimental scanning of AWS vmdk images
- Has integration with popular CI tools

Example commands

```sh
docker run aquasec/trivy image johscheuer/todo-app-web --format cyclonedx > johscheuer-todo-app-web.json
docker run aquasec/trivy image johscheuer/todo-app-web --format cyclonedx --security-checks vuln > johscheuer-todo-app-web.json

docker run aquasec/trivy image nginx --format cyclonedx > nginx.json
docker run aquasec/trivy image nginx --format cyclonedx --security-checks vuln > nginx-vuln.json

docker run aquasec/trivy image postgres --format cyclonedx > postgres.json
docker run aquasec/trivy image postgres --format cyclonedx --security-checks vuln > postgres-vuln.json

docker run aquasec/trivy image qjuanp/t-multi-client --format cyclonedx > qjuanp-t-multi-client-latest.json
docker run aquasec/trivy image qjuanp/t-multi-client --format cyclonedx --security-checks vuln > qjuanp-t-multi-client-latest-vuln.json
```