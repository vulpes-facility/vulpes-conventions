# Cloud providers

1. Write all cloud resources as code with Terraform or OpenTofu.\
   Do not change resources in the console.
2. Keep one state for each environment, in a remote backend with a lock.
3. Give apps cloud access through roles: AWS IAM roles, OCI instance principals or workload identity.\
   Do not use static keys.\
   Some services accept only static keys, for example the S3 Compatibility API of OCI (Customer Secret Keys).\
   For such a service, give each app its own key.\
   Keep the key in the secret service, and replace it on a schedule.
4. Keep secrets in the secret service of the cloud.\
   Give them to the app as environment variables at startup.
5. In app code, use only open protocols: PostgreSQL, the MongoDB wire protocol, RESP (Redis and Valkey), the S3 API, the Kafka API, AMQP, and OTLP.\
   Keep the code of one provider in `infra/`.

| Need | AWS | OCI |
| --- | --- | --- |
| Containers | EKS, ECS | OKE, Container Instances |
| PostgreSQL | RDS, Aurora PostgreSQL | OCI Database with PostgreSQL |
| MongoDB | DocumentDB (MongoDB-compatible) | Oracle Database API for MongoDB (no `$jsonSchema`) |
| Redis or Valkey | ElastiCache | OCI Cache |
| RabbitMQ | Amazon MQ for RabbitMQ | None: run it yourself ([kubernetes.md](kubernetes.md) or [servers.md](servers.md)) |
| Kafka | Amazon MSK | OCI Streaming with Apache Kafka |
| Object storage | S3 | Object Storage (S3 Compatibility API) |
| Secrets | Secrets Manager | Secret Management (secrets in a vault) |
| Image registry | ECR | Container Registry (OCIR) |
| Load balancer, WAF | Application Load Balancer, AWS WAF | Load Balancer, Web Application Firewall |
| Certificates | Certificate Manager | Certificates |
| Observability | CloudWatch, X-Ray through the AWS Distro for OpenTelemetry | Logging, Monitoring, APM (OpenTelemetry) |

- A compatible service is not the original.\
  Run the integration tests against the service that you deploy to.
