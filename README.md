# Apache Package
Apache HTTP Server is an open-source HTTP server. The goal of this project is to provide a secure, efficient and extensible server that provides HTTP services in sync with the current HTTP standards.

## Configuration Reference

You can configure the following:

### Apache parameters
|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|pullPolicy|Apache image pull policy|sting|IfNotPresent|
|Replicas|Number of replicas of the Apache deployment|integer|1|
|hostAliases|Add deployment host aliases|string|""|
|podSecurityContext.fsGroup|Set Apache Server pod's Security Context fsGroup|integer|1001|
|livenessProbe.initialDelaySeconds|Initial delay seconds for livenessProbe|integer|180|
|livenessProbe.periodSeconds|Period seconds for livenessProbe	|integer|20|
|livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|integer|5|
|livenessProbe.successThreshold|Success threshold for livenessProbe|integer|1|
|livenessProbe.failureThreshold|Failure threshold for livenessProbe|integer|6|
|livenessProbe.path|Path to access on the HTTP server|string|/|
|readinessProbe.initialDelaySeconds|Initial delay seconds for readinessProbe	|integer|30|
|readinessProbe.periodSeconds|Period seconds for readinessProbe|integer|10|
|readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|integer|5|
|readinessProbe.successThreshold|Success threshold for readinessProbe|integer|1|
|readinessProbe.failureThreshold|Failure threshold for readinessProbe|integer|6|
|readinessProbe.port|Port for readinessProbe|string|http|
|containerPorts.http|Apache server HTTP container port|integer|8080|
|containerPorts.https|Apache server HTTPS container port|integer|8443|
|containerSecurityContext.runAsUser|Set Apache Server containers' Security Context runAsUser|integer|1001|
|containerSecurityContext.runAsNonRoot|Set Controller container's Security Context runAsNonRoot|string|true|
