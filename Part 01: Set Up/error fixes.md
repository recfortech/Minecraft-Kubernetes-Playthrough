## Error
>recfortech@DESKTOP-LC5RJJV:~/project files$ kubectl apply -f deployment.yaml
>Error from server (BadRequest): error when creating "deployment.yaml": Deployment in version "v1" cannot be handled as a Deployment: >json: cannot unmarshal bool into Go struct field EnvVar.spec.template.spec.containers.env.value of type string
>
### Fix
You are attempting to assign a boolean value (e.g., true or false) to an environment variable in your deployment.yaml where Kubernetes expects a string. The value field for an EnvVar in a container's environment (spec.template.spec.containers.env) is defined as a string type in the Kubernetes API.

Identify boolean values: Look for any value fields that are set to true or false without being enclosed in double quotes.
Enclose in quotes: Change these values to "true" or "false" to explicitly define them as strings.
Apply the updated YAML: Save the deployment.yaml and re-apply it using kubectl apply -f deployment.yaml.

---
## Error: Servcie file.yaml 
>recfortech@DESKTOP-LC5RJJV:~/project files$ kubectl apply -f services.yaml
>error: unable to decode "services.yaml": json: cannot unmarshal array into Go struct field metadataOnlyObject.metadata of type >v1.ObjectMeta
>
>recfortech@DESKTOP-LC5RJJV:~/project files$ kubectl apply -f deployment.yaml
>deployment.apps/minecraft-server unchanged
>Error from server (BadRequest): error when creating "deployment.yaml": service in version "v1" cannot be handled as a Service: no >kind "service" is registered for version "v1" in scheme "pkg/api/legacyscheme/scheme.go:30"
>
>recfortech@DESKTOP-LC5RJJV:~/project files$ kubectl apply -f services.yaml
>Error from server (BadRequest): error when creating "services.yaml": Service in version "v1" cannot be handled as a Service: strict >decoding error: unknown field "environment", unknown field "volumes"

### Fix
Use correct syntax

---


