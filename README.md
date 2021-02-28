## Custom metrics collection using Prometheus on Amazon ECS

This Git repository contains software artifacts to deploy Prometheus server and Prometheus Node Exporter to an Amazon ECS cluster. The Golang code pertains to that of a side-car container that is deployed alongside the Prometheus server in an ECS task and it enables dynamic discovery of scraping targets in the ECS cluster.

<img class="wp-image-1960 size-full" src="images/Depoloyment-Architecture.png" alt="Deployment architecture" width="854" height="527" />

### Solution overview

At a high level, we will be following the steps outlined below for this solution:

<ul>
  <li>
    Setup AWS Cloud Map for service discovery 
  </li>
  <li>
    Deploy application services to an Amazon ECS and register them with AWS Cloud Map
  </li>
  <li>
    Deploy Prometheus server to Amazon ECS, configure service discovery and send metrics data to Amazon Managed Service for Prometheus
  </li>
  <li>
    Visualize metrics data using Amazon Managed Service for Grafana
  </li>  
</ul>

The [deploy](https://github.com/aws-samples/prometheus-for-ecs/tree/main/deploy) directory contains artifacts to deploy a solution stack that comprises the following components:
<ul>
  <li>An ECS task comprising the Prometheus server, AWS Sig4 proxy and the service discovery application containers</li>
  <li>A stateless web application that is instrumented with Prometheus client library. The service exposes a Counter and a Histogram named</li>
  <li>Prometheus Node Exporterto monitor system metrics from every container instance in the cluster</li>
</ul>




## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

