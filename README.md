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

### Traffic Exposure parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|ingress.pathType|Ingress path type|string|ImplementationSpecific|
|ingress.path|Default path for the ingress record|string|/|

### Other Parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|autoscaling.minReplicas|Minimum number of replicas to scale back|integer|1|
|autoscaling.maxReplicas|Maximum number of replicas to scale out|integer|11|
|autoscaling.targetCPU|Target CPU utilization percentage|integer|50|
|autoscaling.targetMemory|Target Memory utilization percentage|integer|50|

#### Metrics Parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|metrics.enabled|Start a sidecar prometheus exporter to expose Apache metrics|string|false|
|metrics.serviceMonitor.enabled|if true, creates a Prometheus Operator PodMonitor (also requires metrics.enabled to be true|string|false|
|metrics.prometheusRule.enabled|if true, creates a Prometheus Operator PodMonitor (also requires metrics.enabled to be true and metrics.prometheusRule.rules)|string|false|
|metrics.prometheusRule.namespace|Namespace for the PrometheusRule Resource (defaults to the Release Namespace)|string|""|
|metrics.prometheusRule.labels|Labels that can be used so PrometheusRule will be discovered by Prometheus|string|{}|
|metrics.prometheusRule.rules|Prometheus Rule definitions|string|[]|





