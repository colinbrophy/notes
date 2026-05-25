# AWS Services — Learning Checklist

Triage for MSP work (law firms + marketing side). Tags:
- ⭐ **Eager learn** — directly applicable, foundational, or imminent
- 💤 **Lazy learn** — know it exists, learn on demand
- ❌ **Don't learn** — irrelevant to current/foreseeable work

---

## ⭐ Eager Learn — foundational & imminent

### Core account & governance (already in flight)
- [ ] AWS Organizations
- [ ] IAM
- [ ] IAM Identity Center
- [ ] CloudTrail
- [ ] AWS Config
- [ ] Control Tower
- [ ] Service Control Policies *(via Organizations)*
- [ ] Service Quotas
- [ ] Resource Access Manager (RAM)
- [ ] AWS Artifact *(SOC 2 / ISO reports for client audits)*

### Security & compliance (law firm table stakes)
- [ ] Key Management Service (KMS)
- [ ] Secrets Manager
- [ ] GuardDuty
- [ ] Security Hub / Security Hub CSPM
- [ ] AWS Backup
- [ ] Certificate Manager (ACM)
- [ ] WAF & Shield
- [ ] Amazon Inspector
- [ ] Amazon Macie *(PII discovery in S3 — relevant for legal docs)*

### Networking foundations
- [ ] VPC
- [ ] Route 53
- [ ] CloudFront
- [ ] API Gateway

### Compute & containers
- [ ] EC2
- [ ] Lambda
- [ ] Elastic Container Service (ECS)
- [ ] Elastic Container Registry (ECR)
- [ ] EC2 Image Builder *(golden AMIs — fits your Ansible philosophy)*

### Storage
- [ ] S3
- [ ] EFS
- [ ] AWS Backup *(also listed under security)*

### Database (law firm workloads)
- [ ] Aurora and RDS
- [ ] DynamoDB *(when key-value is the right tool)*
- [ ] ElastiCache

### Operations & IaC
- [ ] CloudFormation *(at least to read — Terraform is your primary)*
- [ ] CloudWatch
- [ ] Systems Manager
- [ ] Resource Groups & Tag Editor
- [ ] Trusted Advisor
- [ ] AWS Health Dashboard

### Cost & billing
- [ ] Billing and Cost Management
- [ ] AWS Marketplace *(procurement awareness)*
- [ ] AWS Compute Optimizer

### Marketing-side relevant
- [ ] Amazon Simple Email Service (SES) *(transactional + marketing email)*
- [ ] Amazon Pinpoint *(campaign tooling)*
- [ ] AWS Amplify *(hosting marketing sites / landing pages)*
- [ ] Amazon EventBridge *(event-driven glue)*
- [ ] Simple Notification Service (SNS)
- [ ] Simple Queue Service (SQS)

---

## 💤 Lazy Learn — know what it is, dive in when needed

### Compute & containers
- [ ] Elastic Beanstalk
- [ ] Batch
- [ ] AWS App Runner
- [ ] Lightsail *(useful to know exists for cheap client side projects)*
- [ ] Elastic Kubernetes Service (EKS) *(skip unless a client demands k8s)*
- [ ] AWS Outposts
- [ ] Serverless Application Repository

### Storage
- [ ] FSx
- [ ] S3 Glacier
- [ ] Storage Gateway
- [ ] AWS Elastic Disaster Recovery
- [ ] Recycle Bin

### Database
- [ ] Aurora DSQL
- [ ] Amazon DocumentDB
- [ ] Amazon MemoryDB
- [ ] Neptune
- [ ] Amazon Keyspaces
- [ ] Amazon Timestream

### Migration & transfer
- [ ] AWS Migration Hub
- [ ] AWS Application Migration Service
- [ ] Application Discovery Service
- [ ] Database Migration Service (DMS)
- [ ] AWS Transfer Family
- [ ] DataSync
- [ ] AWS Snow Family

### Networking
- [ ] Direct Connect
- [ ] Global Accelerator
- [ ] AWS Cloud Map
- [ ] AWS App Mesh
- [ ] Application Recovery Controller

### Security & identity
- [ ] Cognito *(if you build any auth-bearing app)*
- [ ] Directory Service
- [ ] AWS Firewall Manager
- [ ] Detective
- [ ] CloudHSM
- [ ] AWS Audit Manager
- [ ] Security Lake
- [ ] AWS Private Certificate Authority
- [ ] AWS Signer
- [ ] Amazon Verified Permissions
- [ ] AWS Security Incident Response

### Management & governance
- [ ] Service Catalog
- [ ] AWS Auto Scaling
- [ ] AWS Well-Architected Tool
- [ ] AWS Resilience Hub
- [ ] Launch Wizard
- [ ] AWS Resource Explorer
- [ ] AWS License Manager
- [ ] AWS Proton
- [ ] Incident Manager
- [ ] AWS User Notifications
- [ ] Amazon Grafana / Amazon Prometheus *(if you ever standardise observability on AWS rather than self-hosted)*
- [ ] Amazon Q Developer in chat applications *(formerly AWS Chatbot)*

### Application integration
- [ ] Step Functions
- [ ] Amazon AppFlow
- [ ] Amazon MQ
- [ ] Managed Apache Airflow (MWAA)
- [ ] AWS B2B Data Interchange
- [ ] SWF

### Analytics (if marketing pulls you here)
- [ ] Athena
- [ ] AWS Glue
- [ ] Amazon Data Firehose
- [ ] Kinesis
- [ ] QuickSight
- [ ] Amazon OpenSearch Service
- [ ] EMR
- [ ] Amazon Redshift

### Developer tools
- [ ] CloudShell
- [ ] X-Ray
- [ ] CodeArtifact
- [ ] CodeBuild / CodeDeploy / CodePipeline / CodeCommit *(you have Woodpecker; know these for client environments)*
- [ ] AWS FIS (Fault Injection Simulator)
- [ ] AWS AppConfig
- [ ] Cloud9
- [ ] Infrastructure Composer

### ML (general awareness only)
- [ ] Amazon Bedrock *(only ML service worth real attention right now)*
- [ ] Amazon Q Developer
- [ ] Amazon Textract *(legal doc OCR — could be genuinely useful)*
- [ ] Amazon Transcribe
- [ ] Amazon Polly
- [ ] Amazon Translate
- [ ] Amazon Comprehend
- [ ] Amazon SageMaker AI *(awareness)*

### Front-end / mobile
- [ ] AWS AppSync
- [ ] Device Farm
- [ ] Amazon Location Service

### Business apps
- [ ] Amazon WorkMail *(awareness only — you're not migrating clients here)*
- [ ] Amazon WorkDocs
- [ ] AWS End User Messaging
- [ ] AWS AppFabric
- [ ] Amazon Connect Customer *(if a client ever wants a call centre)*
- [ ] Amazon Connect Health
- [ ] Amazon Connect Decisions

### End user computing
- [ ] WorkSpaces *(virtual desktops — could come up for a paranoid client)*
- [ ] WorkSpaces Secure Browser
- [ ] WorkSpaces Thin Client
- [ ] WorkSpaces Applications

### Customer enablement
- [ ] Support
- [ ] AWS IQ
- [ ] AWS re:Post Private

---

## ❌ Don't Learn — not relevant

### Media services *(no AV workloads in scope)*
- [ ] ~~Kinesis Video Streams~~
- [ ] ~~MediaConvert~~
- [ ] ~~MediaLive~~
- [ ] ~~MediaPackage~~
- [ ] ~~MediaStore~~
- [ ] ~~MediaTailor~~
- [ ] ~~MediaConnect~~
- [ ] ~~Elemental Appliances & Software~~
- [ ] ~~Elemental Inference~~
- [ ] ~~Amazon Interactive Video Service~~
- [ ] ~~AWS Deadline Cloud~~

### IoT *(no IoT clients)*
- [ ] ~~IoT Core~~
- [ ] ~~IoT Device Defender~~
- [ ] ~~IoT Device Management~~
- [ ] ~~IoT Greengrass~~
- [ ] ~~IoT SiteWise~~
- [ ] ~~IoT TwinMaker~~
- [ ] ~~IoT Events~~xxx
- [ ] ~~AWS IoT FleetWise~~

### Game development
- [ ] ~~Amazon GameLift Servers~~
- [ ] ~~Amazon GameLift Streams~~

### Robotics / satellite / quantum / blockchain
- [ ] ~~Ground Station~~
- [ ] ~~Amazon Braket~~
- [ ] ~~Amazon Managed Blockchain~~

### Specialised industry
- [ ] ~~AWS HealthLake~~
- [ ] ~~AWS HealthOmics~~
- [ ] ~~AWS HealthImaging~~
- [ ] ~~Amazon Comprehend Medical~~
- [ ] ~~Amazon Bio Discovery~~
- [ ] ~~AWS for SAP~~
- [ ] ~~AWS Mainframe Modernization~~
- [ ] ~~AWS Telco Network Builder~~
- [ ] ~~RTB Fabric~~
- [ ] ~~Amazon Elastic VMware Service~~
- [ ] ~~Oracle Database@AWS~~
- [ ] ~~Red Hat OpenShift Service on AWS~~
- [ ] ~~Parallel Computing Service~~
- [ ] ~~AWS Panorama~~
- [ ] ~~Amazon Monitron~~
- [ ] ~~Amazon Lookout for Equipment~~

### Niche ML
- [ ] ~~Amazon Augmented AI (A2I)~~
- [ ] ~~Amazon Forecast~~
- [ ] ~~Amazon Fraud Detector~~
- [ ] ~~Amazon Kendra~~
- [ ] ~~Amazon Personalize~~
- [ ] ~~Amazon Rekognition~~
- [ ] ~~Amazon Lex~~
- [ ] ~~Amazon CodeGuru~~
- [ ] ~~Amazon DevOps Guru~~
- [ ] ~~Amazon Q Business~~
- [ ] ~~Amazon Q~~ *(standalone consumer assistant — you have Claude)*
- [ ] ~~Amazon Nova Act~~
- [ ] ~~Amazon Bedrock AgentCore~~

### Niche analytics
- [ ] ~~CloudSearch~~ *(superseded by OpenSearch)*
- [ ] ~~AWS Data Exchange~~
- [ ] ~~AWS Lake Formation~~
- [ ] ~~MSK~~ *(unless you go down a Kafka rabbit hole)*
- [ ] ~~AWS Glue DataBrew~~
- [ ] ~~Amazon FinSpace~~
- [ ] ~~Managed Apache Flink~~
- [ ] ~~AWS Clean Rooms~~
- [ ] ~~Amazon SageMaker (the new unified one)~~
- [ ] ~~AWS Entity Resolution~~
- [ ] ~~Amazon DataZone~~
- [ ] ~~Amazon Quick~~

### Misc
- [ ] ~~AWS Wickr~~
- [ ] ~~Amazon Chime~~
- [ ] ~~Amazon Chime SDK~~
- [ ] ~~AWS Global View~~
- [ ] ~~Amazon Route 53 Global Resolver~~
- [ ] ~~AWS Data Transfer Terminal~~
- [ ] ~~AWS Transform~~
- [ ] ~~AWS App Studio~~
- [ ] ~~AWS DevOps Agent~~
- [ ] ~~Amazon CodeCatalyst~~
- [ ] ~~Kiro~~
- [ ] ~~AWS Payment Cryptography~~
- [ ] ~~AWS Security Agent~~
- [ ] ~~AWS Billing Conductor~~ *(for AWS resellers, not MSPs)*
- [ ] ~~Activate for Startups~~
- [ ] ~~Managed Services~~ *(AMS — enterprise-scale managed)*
- [ ] ~~AWS Sustainability~~
- [ ] ~~AWS Partner Central~~

---

## Notes

- The "eager" list maps roughly to the AWS Solutions Architect Associate scope plus what you'd need for a security-conscious MSP. If certifications matter to clients, SAA + Security Specialty would cover most of the eager column.
- Marketing-side picks (SES, Pinpoint, Amplify, EventBridge) assume you'll end up running campaign infra, transactional email, and marketing landing pages. Adjust if the marketing side is purely SaaS-consumer rather than infra-needing.
- Several "don't learn" items might shift to "lazy learn" if a specific client need surfaces — this is a snapshot, not a permanent verdict.