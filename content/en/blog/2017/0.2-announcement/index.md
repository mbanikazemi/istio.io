---
title: Announcing Istio 0.2
description: Istio 0.2 announcement.
publishdate: 2017-10-10
subtitle: Improved mesh and support for multiple environments
attribution: The Istio Team
aliases:
    - /blog/istio-0.2-announcement.html
---

We launched Istio; an open platform to connect, manage, monitor, and secure microservices, on May 24, 2017. We have been humbled by the incredible interest, and
rapid community growth of developers, operators, and partners. Our 0.1 release was focused on showing all the concepts of Istio in Kubernetes.

Today we are happy to announce the 0.2 release which improves stability and performance, allows for cluster wide deployment and automated injection of sidecars in Kubernetes, adds policy and authentication for TCP services, and enables expansion of the mesh to include services deployed in virtual machines. In addition, Istio can now run outside Kubernetes, leveraging Consul/Nomad or Eureka. Beyond core features, Istio is now ready for extensions to be written by third party companies and developers.

## Highlights for the 0.2 release

### Usability improvements

* _Multiple namespace support_: Istio now works cluster-wide, across multiple namespaces and this was one of the top requests from community from 0.1 release.

* _Policy and security for TCP services_: In addition to HTTP, we have added transparent mutual TLS authentication and policy enforcement for TCP services as well. This will allow you to secure more of your
Kubernetes deployment, and get Istio features like telemetry, policy and security.

* _Automated sidecar injection_: By leveraging the alpha [initializer](https://kubernetes.io/docs/reference/access-authn-authz/extensible-admission-controllers/) feature provided by Kubernetes 1.7, envoy sidecars can now be automatically injected into application deployments when your cluster has the initializer enabled.  This enables you to deploy microservices using `kubectl`, the exact same command that you normally use for deploying the microservices without Istio.

* _Extending Istio_: An improved Mixer design that lets vendors write Mixer adapters to implement support for their own systems, such as application
management or policy enforcement. The
[Mixer Adapter Developer's Guide](https://github.com/istio/istio/wiki/Mixer-Compiled-In-Adapter-Dev-Guide) can help
you easily integrate your solution with Istio.

* _Bring your own CA certificates_: Allows users to provide their own key and certificate for Istio CA and persistent CA key/certificate Storage. Enables storing signing key/certificates in persistent storage to facilitate CA restarts.

* _Improved routing & metrics_: Support for WebSocket, MongoDB and Redis  protocols. You can apply resilience features like circuit breakers on traffic to third party services. In addition to Mixer’s metrics, hundreds of metrics from Envoy are now visible inside Prometheus for all traffic entering, leaving and within Istio mesh.

### Cross environment support

* _Mesh expansion_: Istio mesh can now span services running outside of Kubernetes - like those running in virtual machines while enjoying benefits such as automatic mutual TLS authentication, traffic management, telemetry, and policy enforcement across the mesh.

* _Running outside Kubernetes_: We know many customers use other service registry and orchestration solutions like Consul/Nomad and Eureka. Istio Pilot can now run standalone outside Kubernetes, consuming information from these systems, and manage the Envoy fleet in VMs or containers.

## Get involved in shaping the future of Istio

We have a growing [roadmap](/about/feature-stages/) ahead of us, full of great features to implement. Our focus next release is going to be on stability, reliability, integration with third party tools and multicluster use cases.

To learn how to get involved and contribute to Istio's future, check out our [community](https://github.com/istio/community) GitHub repository which
will introduce you to our working groups, our mailing lists, our various community meetings, our general procedures and our guidelines.

We want to thank our fantastic community for field testing new versions, filing bug reports, contributing code, helping out other community members, and shaping Istio by participating in countless productive discussions. This has enabled the project to accrue 3000 stars on GitHub since launch and hundreds of active community members on Istio mailing lists.

Thank you
