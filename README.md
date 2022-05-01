# Kubernetes Discovery Issue

With following dependencies:

```xml
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-kubernetes-discovery</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-webflux</artifactId>
        </dependency>
```

the application startup fails with the following error

```text

***************************
APPLICATION FAILED TO START
***************************

Description:

Parameter 0 of method kubernetesReactiveDiscoveryClientHealthIndicator in org.springframework.cloud.kubernetes.discovery.KubernetesDiscoveryClientAutoConfiguration$Reactive required a bean of type 'org.springframework.cloud.kubernetes.discovery.KubernetesReactiveDiscoveryClient' that could not be found.


Action:

Consider defining a bean of type 'org.springframework.cloud.kubernetes.discovery.KubernetesReactiveDiscoveryClient' in your configuration.

```

Consider replacing first argument _KubernetesReactiveDiscoveryClient client_ of [kubernetesReactiveDiscoveryClientHealthIndicator](https://github.com/spring-cloud/spring-cloud-kubernetes/blob/01eaac9e43708b7386dc11bb234c5d537a2dc8c2/spring-cloud-kubernetes-discovery/src/main/java/org/springframework/cloud/kubernetes/discovery/KubernetesDiscoveryClientAutoConfiguration.java#L104)
with _ReactiveDiscoveryClient client_.
