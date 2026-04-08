# CST8917 – Serverless Applications Assignment 2 – Serverless Service Alternatives Report
## Akash Nadackanal Vinod - 041156265

---

## Introduction
In this course, we worked with Azure serverless services and built applications using them. This report compares those Azure services with similar services in AWS and Google Cloud.
The goal is not to force exact matches (because they don’t exist in all cases), but to find the closest equivalents and compare how they actually work. The services covered are Azure Functions, Durable Functions, Logic Apps, Service Bus, Event Grid, and Event Hubs.

---

## 1. Azure Functions  
**Azure service:** Azure Functions  
**AWS equivalent:** AWS Lambda  
**GCP equivalent:** Cloud Run functions  

Azure Functions is an event-driven compute service where functions run based on triggers like HTTP, timers, queues, or events. Each function has one trigger and can have multiple bindings.

AWS Lambda is the closest equivalent since it also runs code based on events. GCP Cloud Run functions works similarly, but event handling is often managed through Eventarc.

### Comparison

| Category | Azure Functions | AWS Lambda | GCP Cloud Run functions |
|---|---|---|---|
| Trigger model | Single trigger + bindings | Event sources | Eventarc / HTTP / PubSub |
| Integration | Built-in bindings | Manual integrations | Eventarc + services |
| Monitoring | Application Insights | CloudWatch | Cloud Logging |
| Pricing | Execution-based | Request + duration | Resource usage |

### Analysis
Azure Functions is easier to integrate due to bindings. AWS Lambda is more flexible but requires more setup. GCP is clean but slightly more distributed across services.

---

## 2. Durable Functions  
**Azure service:** Durable Functions  
**AWS equivalent:** AWS Step Functions  
**GCP equivalent:** Google Cloud Workflows  

Durable Functions extends Azure Functions to support stateful workflows such as chaining, orchestration, and fan-out/fan-in patterns.

AWS Step Functions and Google Workflows provide similar workflow orchestration capabilities.

### Comparison

| Category | Durable Functions | AWS Step Functions | GCP Workflows |
|---|---|---|---|
| Type | Code-based orchestration | State machine | Workflow engine |
| State handling | Yes | Yes | Yes |
| Retry support | Yes | Yes | Yes |
| Pricing | Execution-based | State transitions | Steps executed |

### Analysis
Durable Functions integrates directly into application code. Step Functions and Workflows are external orchestration services, which makes them easier to visualize but separate from the main code.

---

## 3. Azure Logic Apps  
**Azure service:** Azure Logic Apps  
**AWS equivalent:** AWS Step Functions (partial)  
**GCP equivalent:** Google Workflows (partial)  

Logic Apps is mainly used for automation and integration, especially with external services like email, SaaS apps, and enterprise systems.

Step Functions and Workflows only cover orchestration and do not provide the same connector ecosystem.

### Comparison

| Category | Logic Apps | Step Functions | Workflows |
|---|---|---|---|
| Purpose | Automation + integration | Orchestration | Orchestration |
| Connectors | Very large | Limited | Limited |
| Low-code | Strong | Medium | Medium |

### Analysis
Logic Apps is better for real-world business workflows. AWS and GCP alternatives are more focused on backend orchestration rather than integration.

---

## 4. Azure Service Bus  
**Azure service:** Azure Service Bus  
**AWS equivalent:** Amazon SQS + SNS  
**GCP equivalent:** Google Pub/Sub  

Azure Service Bus supports queues and topics/subscriptions. AWS requires both SQS (queues) and SNS (pub/sub) to match this functionality.

### Comparison

| Category | Service Bus | SQS + SNS | Pub/Sub |
|---|---|---|---|
| Queue support | Yes | SQS | Subscription-based |
| Pub/Sub | Yes | SNS | Yes |
| Reliability | High | High | High |

### Analysis
Azure Service Bus is more unified. AWS splits functionality into two services. Pub/Sub is simpler but slightly different in behavior.

---

## 5. Azure Event Grid  
**Azure service:** Azure Event Grid  
**AWS equivalent:** Amazon EventBridge  
**GCP equivalent:** Google Eventarc  

Event Grid is used to route events between services.

### Comparison

| Category | Event Grid | EventBridge | Eventarc |
|---|---|---|---|
| Purpose | Event routing | Event routing | Event routing |
| Filtering | Yes | Yes | Yes |
| Targets | Functions, Logic Apps | Lambda, services | Cloud Run |

### Analysis
All three services are very similar. This is one of the closest matches across cloud providers.

---

## 6. Azure Event Hubs  
**Azure service:** Azure Event Hubs  
**AWS equivalent:** Amazon Kinesis Data Streams  
**GCP equivalent:** Google Pub/Sub  

Event Hubs is used for high-throughput streaming (logs, telemetry, IoT).

### Comparison

| Category | Event Hubs | Kinesis | Pub/Sub |
|---|---|---|---|
| Streaming | Yes | Yes | Yes |
| Throughput | High | High | High |
| Model | Partitions | Shards | Topics |

### Analysis
Event Hubs and Kinesis are very similar. Pub/Sub works for similar use cases but is more general-purpose messaging.

---

## Final Summary

| Azure | AWS | GCP |
|---|---|---|
| Functions | Lambda | Cloud Run functions |
| Durable Functions | Step Functions | Workflows |
| Logic Apps | Step Functions (partial) | Workflows (partial) |
| Service Bus | SQS + SNS | Pub/Sub |
| Event Grid | EventBridge | Eventarc |
| Event Hubs | Kinesis | Pub/Sub |

---

## Conclusion
All three cloud providers support serverless architecture, but they structure their services differently. Azure focuses more on integration and abstraction. AWS separates services into smaller components, while GCP keeps things simpler but more general.
Because of this, moving between cloud providers often requires redesigning parts of the architecture instead of directly replacing services.

---

## References

### Azure
- Azure Functions triggers and bindings  
  https://learn.microsoft.com/en-us/azure/azure-functions/functions-triggers-bindings  
- Durable Functions overview  
  https://learn.microsoft.com/en-us/azure/azure-functions/durable-functions-overview  
- Azure Logic Apps overview  
  https://learn.microsoft.com/en-us/azure/logic-apps/logic-apps-overview  
- Azure Service Bus queues, topics, subscriptions  
  https://learn.microsoft.com/en-us/azure/service-bus-messaging/service-bus-queues-topics-subscriptions  
- Azure Event Grid overview  
  https://learn.microsoft.com/en-us/azure/event-grid/overview  
- Azure Event Hubs overview  
  https://learn.microsoft.com/en-us/azure/event-hubs/event-hubs-about  

### AWS
- AWS Lambda  
  https://docs.aws.amazon.com/lambda/latest/dg/welcome.html  
- AWS Step Functions  
  https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html  
- Amazon SQS  
  https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html  
- Amazon SNS  
  https://docs.aws.amazon.com/sns/latest/dg/welcome.html  
- Amazon EventBridge  
  https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html  
- Amazon Kinesis Data Streams  
  https://docs.aws.amazon.com/streams/latest/dev/introduction.html  

### GCP
- Cloud Run functions overview  
  https://cloud.google.com/functions/docs/concepts/overview  
- Google Cloud Workflows  
  https://cloud.google.com/workflows/docs/overview  
- Google Cloud Pub/Sub  
  https://cloud.google.com/pubsub/docs/overview  
- Google Eventarc  
  https://cloud.google.com/eventarc/docs/overview

## AI Disclosure

AI tools were used to assist in formatting this report into Markdown (README.md) format and improving overall structure and clarity. All research, comparisons, and final content were reviewed and verified manually.
