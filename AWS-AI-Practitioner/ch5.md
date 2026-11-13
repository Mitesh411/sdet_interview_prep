## Domain 5: Security, Compliance, and Governance

**Domain 5 index:** [Task 5.1](#task-51-securing-ai-systems) (Q421–Q480) · [Task 5.2](#task-52-governance-and-compliance) (Q481–Q525)

### Task 5.1: Securing AI systems

#### Q421 · Domain 5 · Easy · Multiple Choice
Under the AWS shared responsibility model, which task is AWS responsible for when a customer uses Amazon Bedrock?

- A. Deciding which employees can invoke models
- B. Classifying the sensitivity of the customer's prompts
- C. Securing the physical data centers, hardware, and underlying infrastructure that run the service
- D. Writing the customer's acceptable use policy

<details><summary>Show answer</summary>

**Answer: C**

AWS is responsible for security **of** the cloud: facilities, hardware, networking, and the managed service infrastructure. Customers are responsible for security **in** the cloud, which includes access management, data classification, configuration, and how they use AI outputs.

</details>

#### Q422 · Domain 5 · Medium · Multiple Choice
A data science team uses Amazon SageMaker AI notebooks, training jobs, and endpoints. Which responsibility belongs to the **customer**?

- A. Configuring IAM permissions, encryption settings, and network access (such as VPC settings) for their SageMaker AI resources
- B. Replacing failed hardware in AWS data centers
- C. Patching the physical network switches AWS uses
- D. Securing the hypervisor of the underlying hosts

<details><summary>Show answer</summary>

**Answer: A**

With managed services, AWS handles the infrastructure. Customers still choose and configure identity, encryption, networking, and data protection for their own resources.

</details>

#### Q423 · Domain 5 · Easy · Multiple Choice
What is the primary purpose of AWS Identity and Access Management (IAM) in an AI solution?

- A. To train models faster
- B. To store embeddings
- C. To translate text
- D. To control who (users, roles, services) can access which AWS resources and actions

<details><summary>Show answer</summary>

**Answer: D**

IAM manages authentication and authorization through users, groups, roles, and policies. It is the foundation for controlling access to services such as Amazon Bedrock, SageMaker AI, and the S3 buckets that hold training data.

</details>

#### Q424 · Domain 5 · Medium · Multiple Choice
A developer's IAM role has `AdministratorAccess`, but the developer only needs to invoke one Bedrock model. Which security principle does this violate?

- A. Defense in depth
- B. Least privilege
- C. Data residency
- D. High availability

<details><summary>Show answer</summary>

**Answer: B**

Least privilege means granting only the permissions required for a task. Overly broad permissions increase the damage that compromised credentials or mistakes can cause.

</details>

#### Q425 · Domain 5 · Medium · Multiple Choice
A SageMaker AI training job needs to read training data from Amazon S3 and write model artifacts back to S3. What is the recommended way to grant this access?

- A. Embed an IAM user's access keys in the training script.
- B. Make the S3 bucket public.
- C. Assign the job an IAM execution role with permissions limited to the required buckets and actions.
- D. Share the root user's credentials with the job.

<details><summary>Show answer</summary>

**Answer: C**

SageMaker AI assumes an IAM execution role to access other AWS resources. Scoping that role to specific buckets and actions follows least privilege and avoids long-term credentials in code.

</details>

#### Q426 · Domain 5 · Medium · Multiple Choice
A company wants its application role to invoke **only** two approved foundation models in Amazon Bedrock. How can it enforce this?

- A. Write an IAM policy that allows `bedrock:InvokeModel` only on the ARNs of the two approved models.
- B. Increase the temperature for unapproved models.
- C. Use a larger context window.
- D. Ask developers not to use other models.

<details><summary>Show answer</summary>

**Answer: A**

IAM policies can restrict Bedrock actions to specific resource ARNs, such as particular foundation models or inference profiles. This technically enforces model approval decisions instead of relying on developers to follow guidance.

</details>

#### Q427 · Domain 5 · Hard · Multiple Choice
A company with 40 AWS accounts in AWS Organizations must guarantee that no account can use foundation models that haven't been approved, even if a local administrator grants broad IAM permissions. Which control fits?

- A. An IAM policy in a single account
- B. A Bedrock Guardrails word filter
- C. Model invocation logging
- D. A service control policy (SCP) that denies Bedrock invocation of unapproved models across the organization's accounts

<details><summary>Show answer</summary>

**Answer: D**

SCPs set the maximum permissions available to accounts in an organization. A deny in an SCP applies even when local IAM policies allow the action, which makes SCPs the right tool for organization-wide guardrails.

</details>

#### Q428 · Domain 5 · Easy · Multiple Choice
Which practice adds an extra layer of protection to console sign-in for users who manage AI resources?

- A. Sharing passwords among the team
- B. Enabling multi-factor authentication (MFA)
- C. Disabling password policies
- D. Using the root user for daily work

<details><summary>Show answer</summary>

**Answer: B**

MFA requires a second factor in addition to a password, which greatly reduces the risk of account takeover. AWS recommends MFA for all human users, especially privileged ones, and avoiding root user use for everyday tasks.

</details>

#### Q429 · Domain 5 · Easy · Multiple Choice
Which AWS service is used to create and manage the cryptographic keys that encrypt training data, model artifacts, and knowledge base data at rest?

- A. AWS Key Management Service (AWS KMS)
- B. Amazon Polly
- C. Amazon Route 53
- D. AWS Glue

<details><summary>Show answer</summary>

**Answer: A**

AWS KMS creates and controls encryption keys and integrates with S3, SageMaker AI, Bedrock, and many other services to encrypt data at rest. All key usage is logged in AWS CloudTrail.

</details>

#### Q430 · Domain 5 · Medium · Multiple Choice
A bank requires full control over key policies, key rotation, and the ability to disable access to the keys that encrypt its fine-tuned Bedrock models. Which option meets this requirement?

- A. Rely only on default AWS owned keys.
- B. Store the model unencrypted.
- C. Use a customer managed KMS key for the custom model and related resources.
- D. Encrypt the data with a password in a text file.

<details><summary>Show answer</summary>

**Answer: C**

Customer managed keys let you define key policies, control rotation, audit usage, and revoke access by disabling the key. AWS owned keys are convenient, but you cannot manage them.

</details>

#### Q431 · Domain 5 · Medium · Multiple Choice
How is data protected **in transit** between an application and Amazon Bedrock?

- A. It is not protected.
- B. By compressing the data
- C. By using a higher temperature
- D. By TLS encryption on API connections

<details><summary>Show answer</summary>

**Answer: D**

AWS service endpoints use TLS to encrypt data moving between clients and services. Encryption in transit protects prompts and responses from interception.

</details>

#### Q432 · Domain 5 · Easy · True/False
True or False: Amazon Bedrock encrypts customer data both in transit and at rest.

- A. True
- B. False

<details><summary>Show answer</summary>

**Answer: A (True)**

Bedrock uses TLS for data in transit and encrypts stored data, such as custom models and knowledge base resources, at rest. For stored resources, you can use customer managed KMS keys for additional control.

</details>

#### Q433 · Domain 5 · Easy · Multiple Choice
Which AWS service uses machine learning and pattern matching to discover and report sensitive data, such as PII, stored in Amazon S3?

- A. Amazon Inspector
- B. Amazon Macie
- C. AWS Trusted Advisor
- D. Amazon Lex

<details><summary>Show answer</summary>

**Answer: B**

Amazon Macie scans S3 buckets to identify sensitive data such as names, addresses, credit card numbers, and credentials. It also evaluates bucket security posture, for example by flagging public access.

</details>

#### Q434 · Domain 5 · Medium · Multiple Choice
Before using thousands of customer documents in S3 to fine-tune a model, a company wants to confirm that the documents don't contain unexpected personal data. What should it do first?

- A. Start fine-tuning immediately.
- B. Increase the number of epochs.
- C. Run Amazon Macie sensitive-data discovery on the bucket, then remediate any findings.
- D. Use Amazon Polly to read the documents aloud.

<details><summary>Show answer</summary>

**Answer: C**

Scanning training data with Macie before use helps prevent PII from being embedded in a model, where it could later be disclosed. Findings guide masking, removal, or exclusion of the affected data.

</details>

#### Q435 · Domain 5 · Medium · Multiple Choice
A company requires that traffic from its VPC to Amazon Bedrock never traverses the public internet. Which solution fits?

- A. Create an interface VPC endpoint for Amazon Bedrock using AWS PrivateLink.
- B. Attach an internet gateway.
- C. Use a public IP address for every instance.
- D. Use Amazon CloudFront.

<details><summary>Show answer</summary>

**Answer: A**

AWS PrivateLink provides private connectivity from a VPC to supported AWS services through interface endpoints. Traffic stays on the AWS network, which reduces exposure.

</details>

#### Q436 · Domain 5 · Hard · Multiple Choice
A security team is worried that a third-party training container could send training data to an external server. Which SageMaker AI feature prevents the container from making outbound network calls?

- A. Increasing instance size
- B. Automatic Model Tuning
- C. SageMaker Ground Truth
- D. Network isolation for the training job

<details><summary>Show answer</summary>

**Answer: D**

When network isolation is enabled, the training container cannot make outbound network calls. SageMaker AI still handles moving input and output data to and from S3. This protects against data exfiltration by untrusted code.

</details>

#### Q437 · Domain 5 · Hard · Multiple Choice
A company wants its S3 bucket of training data to be accessible **only** through a specific VPC endpoint, which blocks access from anywhere else, including the internet. How can it enforce this?

- A. Enable S3 Transfer Acceleration.
- B. Add a bucket policy that denies access unless the request comes through that VPC endpoint (using the `aws:SourceVpce` condition).
- C. Rename the bucket.
- D. Use Amazon Polly.

<details><summary>Show answer</summary>

**Answer: B**

Bucket policies with VPC endpoint conditions restrict access to traffic arriving through approved endpoints. Combined with IAM permissions, this is a strong network-level control for sensitive data.

</details>

#### Q438 · Domain 5 · Medium · Multiple Choice
Which S3 feature helps prevent training datasets from being accidentally exposed through public ACLs or bucket policies?

- A. S3 Transfer Acceleration
- B. S3 Select
- C. S3 Block Public Access
- D. S3 Intelligent-Tiering

<details><summary>Show answer</summary>

**Answer: C**

S3 Block Public Access overrides settings that would grant public access, at the bucket or account level. It is a simple, high-impact safeguard for sensitive data.

</details>

#### Q439 · Domain 5 · Medium · Multiple Choice
A GenAI application must call a third-party API that requires a key. Where should the key be stored?

- A. In AWS Secrets Manager, retrieved at runtime by a role with permission to read it
- B. Hardcoded in the application source code
- C. In the model's system prompt
- D. In a public GitHub repository

<details><summary>Show answer</summary>

**Answer: A**

Secrets Manager stores, encrypts, and can rotate secrets, and access is controlled with IAM. Secrets in code, prompts, or repositories are easily leaked.

</details>

#### Q440 · Domain 5 · Medium · Multiple Choice
What does **data lineage** provide for an AI system?

- A. Faster GPUs
- B. Lower token prices
- C. Larger context windows
- D. A record of where data came from, how it was transformed, and which models and outputs used it

<details><summary>Show answer</summary>

**Answer: D**

Data lineage traces data from its sources through processing to training and inference. It supports audits, debugging, compliance, and impact analysis when source data changes or turns out to be problematic.

</details>

#### Q441 · Domain 5 · Medium · Multiple Choice
A company wants a central, searchable inventory of its datasets, including their schemas, locations, and metadata, so that teams can find approved data for ML projects. Which AWS service provides a metadata catalog?

- A. Amazon Polly
- B. AWS Glue Data Catalog
- C. Amazon Rekognition
- D. AWS Snowball

<details><summary>Show answer</summary>

**Answer: B**

The AWS Glue Data Catalog stores table definitions, schemas, and locations for data assets. Cataloging is part of the "documenting data origins" requirement in the exam guide.

</details>

#### Q442 · Domain 5 · Medium · Multiple Choice
For each dataset used to train a model, a team records its source, license terms, collection date, and any consent restrictions. What is the main purpose of this practice?

- A. To reduce GPU memory usage
- B. To make prompts shorter
- C. To support source citation and documented data origins, so the organization can prove that data was used lawfully and appropriately
- D. To increase the temperature

<details><summary>Show answer</summary>

**Answer: C**

Documenting data origins, through source citation, licensing, and consent records, provides accountability. It helps answer audit questions, respond to takedown or deletion requests, and manage IP risk.

</details>

#### Q443 · Domain 5 · Easy · Multiple Choice
What is **data classification** in the context of securing AI systems?

- A. Labeling data by sensitivity level, such as public, internal, confidential, or restricted, so that appropriate controls can be applied
- B. Training a classification model
- C. Sorting files alphabetically
- D. Compressing data

<details><summary>Show answer</summary>

**Answer: A**

Data classification determines which data may be used with which AI services, and which encryption, access, and retention rules apply. It is a customer responsibility and comes before most other data controls.

</details>

#### Q444 · Domain 5 · Medium · Multiple Choice
A team wants automated checks that flag missing values, out-of-range numbers, and schema changes in data pipelines before the data reaches model training. Which AWS capability helps?

- A. Amazon Polly
- B. Amazon Lex
- C. AWS Artifact
- D. AWS Glue Data Quality

<details><summary>Show answer</summary>

**Answer: D**

AWS Glue Data Quality evaluates datasets against rules, such as completeness, uniqueness, and value ranges, and reports or acts on failures. Good data quality is part of secure, reliable data engineering.

</details>

#### Q445 · Domain 5 · Hard · Multiple Choice
An analytics team needs to link a patient's records across several datasets without seeing real names. The organization replaces each name with a consistent random token, and keeps the mapping in a separate, tightly controlled system. Which privacy-enhancing technique is this?

- A. Anonymization, which can never be reversed
- B. Pseudonymization (tokenization)
- C. Data augmentation
- D. Chunking

<details><summary>Show answer</summary>

**Answer: B**

Pseudonymization replaces identifiers with tokens. Records can still be linked, and authorized parties holding the mapping can re-identify them. Anonymization irreversibly removes the ability to identify individuals. Pseudonymized data is often still treated as personal data under privacy laws.

</details>

#### Q446 · Domain 5 · Medium · Multiple Choice
A retailer and a partner brand want to analyze their combined customer data for joint insights and modeling, but neither company is willing to share its raw data with the other. Which AWS service is designed for this?

- A. AWS Clean Rooms
- B. Amazon Polly
- C. Amazon Route 53
- D. AWS Snowball

<details><summary>Show answer</summary>

**Answer: A**

AWS Clean Rooms lets multiple parties collaborate on combined datasets under controlled analysis rules, without exposing their underlying raw data to each other. It is an example of a privacy-enhancing technology.

</details>

#### Q447 · Domain 5 · Medium · Multiple Choice
Auditors require proof that the training dataset used for a production model has not been altered or deleted since training. Which combination supports data integrity?

- A. Public bucket access
- B. Deleting old versions
- C. Higher temperature
- D. S3 Versioning, S3 Object Lock (write-once-read-many), and checksums to verify file integrity

<details><summary>Show answer</summary>

**Answer: D**

Versioning preserves every object version, Object Lock prevents deletion or overwriting for a retention period, and checksums detect tampering. Together they keep the training data verifiable.

</details>

#### Q448 · Domain 5 · Medium · Multiple Choice
Data scientists should be able to query a customer table for model training, but they must not see the "SSN" and "date of birth" columns. Which AWS service provides this kind of fine-grained, column-level access control for a data lake?

- A. Amazon Polly
- B. AWS Lake Formation
- C. Amazon CloudFront
- D. AWS Snowball

<details><summary>Show answer</summary>

**Answer: B**

AWS Lake Formation provides fine-grained permissions at the database, table, column, row, and cell level for data lakes. Users get access only to the data they need.

</details>

#### Q449 · Domain 5 · Hard · Multiple Choice
A company publishes aggregate statistics derived from user data. It wants a mathematical guarantee that no individual's presence in the dataset can be reliably inferred from the published results. Which technique fits?

- A. One-hot encoding
- B. Chain-of-thought prompting
- C. Differential privacy, which adds carefully calibrated noise to results
- D. Increasing the context window

<details><summary>Show answer</summary>

**Answer: C**

Differential privacy provides a formal guarantee that limits how much any single record can affect the output. The trade-off is that the added noise reduces precision.

</details>

#### Q450 · Domain 5 · Medium · Multiple Choice
A team designing a GenAI support assistant decides to send the model only the customer's order number and issue description, not their full profile, address, or payment details. Which principle is this?

- A. Data minimization
- B. Data augmentation
- C. Model distillation
- D. Hyperparameter tuning

<details><summary>Show answer</summary>

**Answer: A**

Data minimization means collecting and processing only the data needed for a purpose. Less sensitive data in prompts, logs, and training sets means less exposure if something goes wrong.

</details>

#### Q451 · Domain 5 · Medium · Multiple Choice
A security team wants continuous threat detection that alerts on suspicious activity, such as compromised credentials or unusual API calls, across the AWS accounts that host its AI workloads. Which service fits?

- A. Amazon Polly
- B. AWS Artifact
- C. AWS Glue
- D. Amazon GuardDuty

<details><summary>Show answer</summary>

**Answer: D**

Amazon GuardDuty analyzes sources such as CloudTrail events, VPC flow logs, and DNS logs to detect threats and anomalous behavior. Threat detection is listed in the exam guide as a security consideration for AI systems.

</details>

#### Q452 · Domain 5 · Medium · Multiple Choice
A company hosts its models in custom container images stored in Amazon ECR. It wants automatic scanning of these images for known software vulnerabilities (CVEs). Which service fits?

- A. Amazon Macie
- B. Amazon Inspector
- C. Amazon Lex
- D. AWS Artifact

<details><summary>Show answer</summary>

**Answer: B**

Amazon Inspector continuously scans Amazon EC2 instances, ECR container images, and Lambda functions for software vulnerabilities and unintended network exposure. Macie, by contrast, finds sensitive data.

</details>

#### Q453 · Domain 5 · Medium · Multiple Choice
A public GenAI API behind Amazon API Gateway is receiving floods of malicious requests from a few IP addresses. Which service helps filter and rate-limit this traffic at the edge?

- A. Amazon Comprehend
- B. Amazon SageMaker Ground Truth
- C. AWS WAF, using managed rules and rate-based rules
- D. AWS Glue

<details><summary>Show answer</summary>

**Answer: C**

AWS WAF is a web application firewall that integrates with API Gateway, Application Load Balancer, and CloudFront. It can block malicious patterns and throttle abusive clients. This is part of infrastructure protection.

</details>

#### Q454 · Domain 5 · Hard · Multiple Choice
A developer stores the rule "Only show account balances to the account owner" in a chatbot's system prompt, and relies on it as the sole access control. What is the main security flaw?

- A. System prompts can be leaked or overridden by prompt attacks, so authorization must be enforced in application code and IAM, outside the model.
- B. System prompts are encrypted, so this is completely safe.
- C. The rule makes the model slower.
- D. The rule increases token cost.

<details><summary>Show answer</summary>

**Answer: A**

System prompt leakage and prompt injection are listed in the OWASP Top 10 for LLM Applications. LLMs are not security boundaries. Enforce authentication and authorization deterministically before data reaches the model.

</details>

#### Q455 · Domain 5 · Medium · Multiple Choice
For audit and troubleshooting purposes, a company needs to capture the full input prompts and output responses of its Amazon Bedrock model calls. Which feature provides this?

- A. Amazon Bedrock playgrounds
- B. AWS Trusted Advisor
- C. Amazon Polly
- D. Amazon Bedrock model invocation logging, delivered to Amazon CloudWatch Logs and/or Amazon S3

<details><summary>Show answer</summary>

**Answer: D**

Model invocation logging, which is disabled by default, records request and response data along with metadata for Bedrock model invocations. It supports auditing, abuse investigation, and quality analysis.

</details>

#### Q456 · Domain 5 · Hard · Multiple Choice
After enabling Bedrock model invocation logging, the security team realizes that the logs contain customer PII from user prompts. What is the most appropriate response?

- A. Disable all security monitoring.
- B. Protect the logs as sensitive data: encrypt them with KMS, restrict access with least-privilege IAM, set retention limits, and consider masking PII before logging.
- C. Make the log bucket public for transparency.
- D. Email the logs to all employees.

<details><summary>Show answer</summary>

**Answer: B**

Logs that capture prompts can contain sensitive data, so they need the same protections as the source data: encryption, access control, retention policies, and minimization. Guardrails' sensitive information filters can also mask PII in prompts and responses.

</details>

#### Q457 · Domain 5 · Medium · Multiple Choice
What is the OWASP Top 10 for Large Language Model Applications?

- A. A ranking of the most accurate LLMs
- B. A list of AWS pricing tiers
- C. A community-developed list of the most critical security risks for LLM applications, such as prompt injection and sensitive information disclosure
- D. A benchmark dataset for summarization

<details><summary>Show answer</summary>

**Answer: C**

The OWASP Top 10 for LLM Applications helps teams identify and mitigate common GenAI vulnerabilities. Examples include prompt injection, sensitive information disclosure, supply chain risks, data and model poisoning, improper output handling, excessive agency, system prompt leakage, vector and embedding weaknesses, misinformation, and unbounded consumption.

</details>

#### Q458 · Domain 5 · Hard · Multiple Choice
An application asks an LLM to write SQL from a user's question, then executes that SQL directly against the production database with full permissions. Which risk is this, and how should it be mitigated?

- A. Improper output handling; treat model output as untrusted by validating and restricting it, and run queries with a read-only, least-privilege database role.
- B. Hallucination; increase the temperature.
- C. Data drift; retrain the model.
- D. Knowledge cutoff; use RAG.

<details><summary>Show answer</summary>

**Answer: A**

LLM outputs can be manipulated, for example through prompt injection, or can simply be wrong. Passing them unchecked to interpreters, databases, or browsers enables attacks. Validation, allow-lists, parameterization, and least privilege reduce the risk.

</details>

#### Q459 · Domain 5 · Hard · Multiple Choice
A Bedrock agent built only to look up order status has been given tools that can also issue refunds, delete accounts, and send emails. Which OWASP LLM risk does this create?

- A. Model theft
- B. Vector and embedding weaknesses
- C. Misinformation
- D. Excessive agency

<details><summary>Show answer</summary>

**Answer: D**

Excessive agency means giving an LLM-based system more functionality, permissions, or autonomy than it needs. If the agent is manipulated, the damage is larger. Limit tools and permissions to the task, and require human approval for high-impact actions.

</details>

#### Q460 · Domain 5 · Hard · Multiple Choice
A company fine-tuned a model on raw support tickets. Testers later find that certain prompts make the model output real customers' phone numbers. What is the root cause, and what is the best prevention?

- A. High temperature; lower it.
- B. The model memorized sensitive training data; scrub or mask PII from training data before fine-tuning, and add output filters.
- C. A small context window; use a larger model.
- D. Missing citations; enable citations.

<details><summary>Show answer</summary>

**Answer: B**

Models can memorize and regurgitate training data. This is the "sensitive information disclosure" risk. Removing PII before training is the most effective control, and output-side PII filters add a second layer.

</details>

#### Q461 · Domain 5 · Medium · Multiple Choice
A competitor sends millions of automated queries to a company's proprietary model API, apparently to collect enough outputs to train a copy of the model. Which controls help reduce this model extraction risk?

- A. Publishing the model weights
- B. Removing authentication
- C. Strong authentication, rate limiting and usage quotas, and monitoring for abnormal query patterns
- D. Increasing the temperature

<details><summary>Show answer</summary>

**Answer: C**

Model extraction relies on high-volume access. Requiring authenticated access, throttling usage, and detecting anomalous patterns make extraction harder and help protect the intellectual property in the model.

</details>

#### Q462 · Domain 5 · Hard · Multiple Response
A company wants to protect its fine-tuning datasets and RAG knowledge base sources from data poisoning. Which TWO measures help most? (Select TWO.)

- A. Restrict write access to training and knowledge base data sources with least-privilege IAM and bucket policies
- B. Allow anyone on the internet to contribute documents to the knowledge base
- C. Disable versioning on the source buckets
- D. Validate and curate incoming data, and track lineage so suspicious changes can be traced and rolled back
- E. Turn off all logging to save cost

<details><summary>Show answer</summary>

**Answer: A, D**

Poisoning requires the ability to insert malicious data. Limiting who can write to data sources, validating content before it is used, and maintaining lineage and versions for detection and rollback are the core defenses.

</details>

#### Q463 · Domain 5 · Hard · Multiple Choice
A SaaS provider stores embeddings for all of its customers in one shared vector index. A user from Company A receives answers containing Company B's documents. Which risk is this, and how should it be fixed?

- A. Vector and embedding weaknesses (cross-tenant data leakage); enforce tenant isolation through separate indexes or mandatory tenant-ID metadata filters, applied server-side
- B. Hallucination; lower the temperature
- C. Catastrophic forgetting; retrain the model
- D. Knowledge cutoff; update the model

<details><summary>Show answer</summary>

**Answer: A**

Multi-tenant RAG systems must isolate data at retrieval time. Without enforced isolation, similarity search can return another tenant's content. The filters must be enforced by the application, never left to the model or the client.

</details>

#### Q464 · Domain 5 · Medium · Multiple Choice
Attackers send extremely long prompts and request maximum-length outputs at high volume, which drives up costs and degrades service for legitimate users. Which controls address this "unbounded consumption" risk?

- A. Remove all quotas.
- B. Increase max tokens.
- C. Disable authentication.
- D. Apply request throttling and usage plans (for example, with Amazon API Gateway), cap input and output token limits, and monitor usage and cost.

<details><summary>Show answer</summary>

**Answer: D**

Rate limits, token caps, per-user quotas, and cost monitoring prevent resource exhaustion and runaway spending. They also protect availability for legitimate users.

</details>

#### Q465 · Domain 5 · Medium · Multiple Choice
Developers want to download an open-source model and a few Python libraries from public repositories to use in production. Which practice reduces supply chain risk?

- A. Download from any unofficial mirror for faster speed.
- B. Use trusted sources, verify the integrity of artifacts, scan dependencies and containers for vulnerabilities, and review licenses before use.
- C. Skip all scanning to save time.
- D. Run the code as the root user.

<details><summary>Show answer</summary>

**Answer: B**

Third-party models and packages can contain vulnerabilities, malicious code, or problematic licenses. Vetting their sources and scanning them, for example with Amazon Inspector for containers, reduces supply chain risk.

</details>

#### Q466 · Domain 5 · Hard · Matching
Match each threat to the AWS service or feature that best addresses it.

| Threat | Control |
|---|---|
| 1. Unnoticed sensitive data in a training bucket | a. Amazon Macie |
| 2. Known vulnerabilities in a model-serving container image | b. Amazon Inspector |
| 3. Malicious API activity from compromised credentials | c. Amazon GuardDuty |
| 4. Jailbreak attempts in user prompts | d. Amazon Bedrock Guardrails prompt attack filter |

- A. 1-b, 2-a, 3-c, 4-d
- B. 1-a, 2-c, 3-b, 4-d
- C. 1-a, 2-b, 3-c, 4-d
- D. 1-d, 2-b, 3-c, 4-a

<details><summary>Show answer</summary>

**Answer: C**

Macie discovers sensitive data (a). Inspector scans for vulnerabilities (b). GuardDuty detects threats (c). Guardrails block prompt attacks (d). Exam questions often test whether you can tell these security services apart.

</details>

#### Q467 · Domain 5 · Medium · Multiple Response
Which TWO measures protect data during SageMaker AI model training? (Select TWO.)

- A. Encrypt ML storage volumes and S3 outputs with AWS KMS keys
- B. Disable TLS on all connections
- C. Store the training data in a public bucket
- D. Enable inter-container traffic encryption for distributed training jobs
- E. Share root user credentials with the training job

<details><summary>Show answer</summary>

**Answer: A, D**

SageMaker AI supports KMS encryption for storage volumes and output artifacts (at rest), and inter-container traffic encryption between nodes in distributed training (in transit). The other options weaken security.

</details>

#### Q468 · Domain 5 · Easy · True/False
True or False: AWS is responsible for deciding which of a customer's employees should have IAM permissions to invoke Amazon Bedrock models.

- A. True
- B. False

<details><summary>Show answer</summary>

**Answer: B (False)**

Identity and access management for a customer's users is the customer's responsibility under the shared responsibility model. AWS provides the IAM service, but customers define who can do what.

</details>

#### Q469 · Domain 5 · Medium · Multiple Choice
An application in Account A needs to read a curated training dataset stored in Account B. What is the recommended approach?

- A. Copy Account B's root user password into the application.
- B. Make the dataset public.
- C. Create an IAM role in Account B that trusts Account A, grant it read access, and have the application assume the role through AWS STS.
- D. Email the data between accounts.

<details><summary>Show answer</summary>

**Answer: C**

Cross-account role assumption provides temporary, scoped credentials without sharing long-term keys. It is the standard secure pattern for access between accounts.

</details>

#### Q470 · Domain 5 · Hard · Multiple Choice
The Lambda function behind a Bedrock agent's action group has an execution role with full administrator permissions. The function only needs to read one DynamoDB table. What is the risk, and what is the fix?

- A. If the agent is manipulated through prompt injection, the attacker gains broad control of the account; scope the Lambda role to read-only access on that single table.
- B. There is no risk, because agents can't be manipulated.
- C. The only risk is higher latency; increase the memory.
- D. The risk is hallucination; add citations.

<details><summary>Show answer</summary>

**Answer: A**

Agent tools inherit the permissions of their execution roles. Least-privilege roles contain the blast radius if the model is tricked into misusing a tool.

</details>

#### Q471 · Domain 5 · Medium · Multiple Choice
A company deploys Amazon Q Business over its HR and finance documents. How does it make sure employees only receive answers drawn from documents they're allowed to see?

- A. Ask employees to promise not to look at restricted content.
- B. Raise the temperature.
- C. Remove all access controls to simplify setup.
- D. Integrate user identity (for example, through AWS IAM Identity Center) and rely on the document access control lists ingested from the connected data sources.

<details><summary>Show answer</summary>

**Answer: D**

Amazon Q Business uses user identity and source-system permissions to filter results, so answers only draw on content the user is authorized to access. This prevents oversharing through the assistant.

</details>

#### Q472 · Domain 5 · Medium · Multiple Choice
An ML platform team wants to quickly create least-privilege IAM roles tailored to personas such as data scientist and MLOps engineer for SageMaker AI. Which tool is designed for this?

- A. Amazon Polly
- B. Amazon SageMaker Role Manager
- C. AWS Snowball
- D. Amazon Translate

<details><summary>Show answer</summary>

**Answer: B**

SageMaker Role Manager provides persona-based templates and guided steps for building least-privilege roles for ML activities. It is one of SageMaker AI's governance tools, along with Model Cards and Model Dashboard.

</details>

#### Q473 · Domain 5 · Hard · Multiple Choice
A company bound by strict data residency rules plans to use Amazon Bedrock cross-Region inference to improve throughput. What should it evaluate first?

- A. Nothing; cross-Region inference never affects where data is processed.
- B. Whether the model supports image generation
- C. Which Regions the chosen inference profile can route requests to, so that processing stays within allowed geographies, for example by using a geography-specific profile or in-Region inference only
- D. The model's default temperature

<details><summary>Show answer</summary>

**Answer: C**

Cross-Region inference can process requests in other Regions within the profile's scope. Organizations with residency requirements must confirm that the routing scope complies, or else avoid cross-Region routing.

</details>

#### Q474 · Domain 5 · Medium · Ordering
Put these secure data-preparation steps for model training in the most appropriate order:

1. Train the model
2. Discover and classify sensitive data (for example, with Amazon Macie)
3. Mask or remove PII that isn't required for the use case
4. Store the prepared data in an encrypted, access-controlled location
5. Record lineage and catalog the dataset

- A. 2 → 3 → 4 → 5 → 1
- B. 3 → 2 → 4 → 5 → 1
- C. 2 → 4 → 3 → 1 → 5
- D. 5 → 2 → 3 → 4 → 1

<details><summary>Show answer</summary>

**Answer: A**

You must first know what sensitive data exists before you can minimize it. Then protect the resulting dataset with encryption and access controls, document its lineage, and only then train. Documenting lineage only after training would leave a gap in traceability.

</details>

#### Q475 · Domain 5 · Easy · True/False
True or False: Placing database passwords in an LLM's system prompt is safe, because users can't see the system prompt.

- A. True
- B. False

<details><summary>Show answer</summary>

**Answer: B (False)**

System prompts can be leaked through prompt attacks or logged in plain text. Secrets belong in a secrets manager and should be used by application code, never placed in model context.

</details>

#### Q476 · Domain 5 · Medium · Multiple Choice
A security team wants a single place to aggregate, prioritize, and track security findings from GuardDuty, Inspector, Macie, and other services across all the accounts that run its AI workloads. Which service fits?

- A. Amazon Polly
- B. Amazon SageMaker Canvas
- C. AWS Glue
- D. AWS Security Hub

<details><summary>Show answer</summary>

**Answer: D**

AWS Security Hub centralizes security findings and runs automated checks against security standards, which gives a consolidated view of security posture across accounts.

</details>

#### Q477 · Domain 5 · Medium · Multiple Choice
A SageMaker AI training job needs to read data from an Amazon RDS database in a private subnet, with no internet access. What is the right configuration?

- A. Run the training job inside the VPC, specifying subnets and security groups that allow access to the database.
- B. Make the database publicly accessible.
- C. Export the database to a public website.
- D. Use Amazon Polly.

<details><summary>Show answer</summary>

**Answer: A**

SageMaker AI jobs can be configured to run within your VPC, so they can reach private resources while the network remains isolated from the internet. Access is controlled through security groups.

</details>

#### Q478 · Domain 5 · Medium · Multiple Choice
A company is building a customer-facing GenAI portal. Users must sign in, and each user should only see their own account information in answers. Which design is most appropriate?

- A. No sign-in; trust whatever account number the user types.
- B. Let the LLM decide which account data each user may see.
- C. Authenticate users (for example, with Amazon Cognito) and have the application retrieve only the authenticated user's data before building the prompt.
- D. Put all customers' data in every prompt.

<details><summary>Show answer</summary>

**Answer: C**

Application security requires deterministic authentication and authorization. Fetching only the authorized user's data before calling the model prevents cross-user data exposure, regardless of how the prompt is manipulated.

</details>

#### Q479 · Domain 5 · Medium · Multiple Choice
A customer asks whether third-party model providers on Amazon Bedrock can see its prompts and responses. Which statement is accurate?

- A. Every model provider receives a copy of all prompts.
- B. Model providers don't have access to customer prompts and completions processed through Amazon Bedrock.
- C. Prompts are posted publicly for research.
- D. Providers can access the data only on weekends.

<details><summary>Show answer</summary>

**Answer: B**

Amazon Bedrock is designed so that model providers have no access to customer data such as prompts and completions. Combined with encryption and the absence of training on customer data, this supports enterprise privacy requirements.

</details>

#### Q480 · Domain 5 · Hard · Multiple Response
Which TWO practices best reflect a defense-in-depth approach for a GenAI application built on Amazon Bedrock? (Select TWO.)

- A. Rely only on the system prompt to block misuse
- B. Apply Amazon Bedrock Guardrails to both user inputs and model outputs
- C. Disable logging to reduce cost
- D. Hardcode credentials in the frontend for convenience
- E. Combine least-privilege IAM with private connectivity, such as AWS PrivateLink, and encryption

<details><summary>Show answer</summary>

**Answer: B, E**

Defense in depth layers independent controls: content safeguards, identity and access controls, network isolation, encryption, and monitoring. A single control, such as a system prompt, is easy to bypass.

</details>

### Task 5.2: Governance and compliance

#### Q481 · Domain 5 · Easy · Multiple Choice
An auditor asks for AWS's SOC 2 and ISO certification reports to support the company's compliance review of its AI platform. Where can the company download these reports?

- A. AWS Artifact
- B. Amazon Polly
- C. Amazon SageMaker Ground Truth
- D. Amazon Translate

<details><summary>Show answer</summary>

**Answer: A**

AWS Artifact provides on-demand access to AWS security and compliance reports, such as SOC, PCI, and ISO, and to agreements such as the Business Associate Addendum (BAA).

</details>

#### Q482 · Domain 5 · Easy · Multiple Choice
Which AWS service records API calls made in an AWS account, including who made each call, when, and from where, to support auditing of AI resource changes?

- A. Amazon Polly
- B. AWS Glue
- C. AWS CloudTrail
- D. Amazon Lex

<details><summary>Show answer</summary>

**Answer: C**

CloudTrail logs account activity, such as creating a Bedrock guardrail or modifying a SageMaker AI endpoint. It is essential for security investigations, governance, and compliance evidence.

</details>

#### Q483 · Domain 5 · Medium · Multiple Choice
A company wants to continuously record the configuration of its AI-related resources, such as S3 buckets and SageMaker AI endpoints, and automatically flag any that drift from required settings. Which service fits?

- A. Amazon Polly
- B. AWS Artifact
- C. Amazon Translate
- D. AWS Config

<details><summary>Show answer</summary>

**Answer: D**

AWS Config tracks resource configurations and their change history, and evaluates them against rules, such as "buckets must be encrypted." It can trigger remediation. Conformance packs bundle rules for common frameworks.

</details>

#### Q484 · Domain 5 · Medium · Multiple Choice
A compliance team spends weeks manually gathering screenshots and logs to prove its controls to auditors. Which AWS service continuously collects evidence and maps it to compliance frameworks?

- A. Amazon Inspector
- B. AWS Audit Manager
- C. Amazon Kendra
- D. Amazon Polly

<details><summary>Show answer</summary>

**Answer: B**

AWS Audit Manager automates evidence collection from AWS services, maps the evidence to controls in prebuilt or custom frameworks, and helps prepare audit-ready reports.

</details>

#### Q485 · Domain 5 · Medium · Multiple Choice
Which AWS service inspects an account and recommends improvements across cost optimization, security, performance, fault tolerance, and service limits?

- A. AWS Trusted Advisor
- B. Amazon Macie
- C. Amazon Comprehend
- D. AWS Clean Rooms

<details><summary>Show answer</summary>

**Answer: A**

Trusted Advisor runs best-practice checks. On the security side, these include checks such as root user MFA, exposed access keys, and overly permissive security groups. It helps maintain a well-governed environment for AI workloads.

</details>

#### Q486 · Domain 5 · Medium · Matching
Match each AWS service with its governance or compliance function.

| Service | Function |
|---|---|
| 1. AWS CloudTrail | a. Resource configuration history and compliance rules |
| 2. AWS Config | b. Logs of API activity in the account |
| 3. AWS Artifact | c. Access to AWS compliance reports and agreements |
| 4. Amazon Inspector | d. Automated vulnerability scanning |

- A. 1-a, 2-b, 3-c, 4-d
- B. 1-b, 2-c, 3-a, 4-d
- C. 1-b, 2-a, 3-d, 4-c
- D. 1-b, 2-a, 3-c, 4-d

<details><summary>Show answer</summary>

**Answer: D**

CloudTrail answers "who did what" (b). Config answers "how resources are configured and whether that complies" (a). Artifact provides "AWS's compliance documents" (c). Inspector answers "what vulnerabilities exist" (d).

</details>

#### Q487 · Domain 5 · Easy · Multiple Choice
Which international standard specifies requirements for establishing and continually improving an **AI management system** within an organization?

- A. ISO/IEC 27001
- B. PCI DSS
- C. ISO/IEC 42001
- D. SOC 1

<details><summary>Show answer</summary>

**Answer: C**

ISO/IEC 42001 is the AI management system standard. It covers AI risk management, impact assessment, and lifecycle governance. ISO/IEC 27001 covers information security management, PCI DSS covers payment card data, and SOC 1 covers controls relevant to financial reporting.

</details>

#### Q488 · Domain 5 · Medium · Multiple Choice
What does a SOC 2 report evaluate?

- A. The accuracy of an ML model
- B. A service organization's controls relevant to security, availability, processing integrity, confidentiality, and privacy
- C. The number of tokens processed per day
- D. The performance of GPU hardware

<details><summary>Show answer</summary>

**Answer: B**

SOC 2 reports assess controls against the Trust Services Criteria. Customers use AWS's SOC reports, available through AWS Artifact, as part of their own compliance assessments.

</details>

#### Q489 · Domain 5 · Medium · Multiple Choice
What do **algorithmic accountability** laws and regulations typically require from organizations that use automated decision systems?

- A. That organizations use the largest available models
- B. That organizations never use AI
- C. That all models be open source
- D. Assessments of impact and bias, transparency about automated decisions, and mechanisms for accountability and redress

<details><summary>Show answer</summary>

**Answer: D**

Algorithmic accountability rules aim to make automated decisions fair, explainable, and contestable. They often require impact assessments, documentation, notice to affected people, and human review options.

</details>

#### Q490 · Domain 5 · Medium · Multiple Choice
How does the European Union's AI Act approach the regulation of AI systems?

- A. It uses a risk-based approach, with stricter obligations for higher-risk uses and prohibitions on certain unacceptable practices.
- B. It bans all AI in the EU.
- C. It regulates only image-generation models.
- D. It applies only to companies with fewer than 10 employees.

<details><summary>Show answer</summary>

**Answer: A**

The EU AI Act classifies AI uses by risk level, from unacceptable (prohibited), to high-risk (strict requirements such as risk management, documentation, and human oversight), to limited and minimal risk. Obligations scale with the potential for harm.

</details>

#### Q491 · Domain 5 · Medium · Multiple Choice
An EU customer exercises their right to have their personal data erased. The company has stored that customer's chat transcripts in its RAG knowledge base and in its prompt logs. What must the company be prepared to do under GDPR?

- A. Ignore the request, because AI systems are exempt.
- B. Delete only the customer's email address from the CRM.
- C. Locate and delete or anonymize the customer's personal data across systems, including knowledge base sources, logs, and any datasets planned for training.
- D. Move the data to another Region.

<details><summary>Show answer</summary>

**Answer: C**

GDPR rights, such as erasure, apply to personal data wherever it is stored. Good data lineage, retention policies, and data minimization make it practical to honor these requests across AI pipelines.

</details>

#### Q492 · Domain 5 · Medium · Multiple Choice
A healthcare company wants to process protected health information (PHI) with AWS AI services. What must it do to align with HIPAA?

- A. Use any AWS service without restrictions.
- B. Use HIPAA-eligible services, accept a Business Associate Addendum (BAA) with AWS, and implement appropriate safeguards in its own configuration.
- C. Store PHI in public buckets.
- D. Avoid encryption, for faster processing.

<details><summary>Show answer</summary>

**Answer: B**

HIPAA compliance on AWS requires a BAA, use of only HIPAA-eligible services for PHI, and customer-implemented controls such as access management, encryption, and logging.

</details>

#### Q493 · Domain 5 · Hard · Multiple Choice
A startup claims, "We run on AWS, which is ISO and SOC certified, so our AI application is automatically compliant." Why is this claim incorrect?

- A. AWS certifications are not real.
- B. Compliance applies only to on-premises systems.
- C. AI applications are always exempt from compliance.
- D. AWS certifications cover AWS's controls; the customer inherits some of those controls but must still implement and evidence its own controls for its applications, data, and processes.

<details><summary>Show answer</summary>

**Answer: D**

Compliance follows the shared responsibility model. AWS's attestations cover the infrastructure and services, while customers remain responsible for how they configure and use those services and for their own governance processes.

</details>

#### Q494 · Domain 5 · Easy · True/False
True or False: Using HIPAA-eligible AWS services automatically makes a company's AI application HIPAA compliant.

- A. True
- B. False

<details><summary>Show answer</summary>

**Answer: B (False)**

Eligibility means a service *can* be used for PHI under a BAA. The customer must still configure it securely and meet HIPAA requirements in its own application and processes.

</details>

#### Q495 · Domain 5 · Medium · Multiple Choice
A company's policy states that raw training data must move to cheaper archival storage after 90 days and be deleted after 3 years. How can this be automated in Amazon S3?

- A. Configure S3 Lifecycle policies with transition and expiration rules.
- B. Delete files manually whenever someone remembers.
- C. Use Amazon Polly.
- D. Increase the bucket's name length.

<details><summary>Show answer</summary>

**Answer: A**

S3 Lifecycle rules automatically transition objects between storage classes and expire them on schedule. This implements data lifecycle and retention policies consistently.

</details>

#### Q496 · Domain 5 · Medium · Multiple Choice
What should a data retention policy for a GenAI application define?

- A. The model's temperature
- B. The chunk size for embeddings
- C. How long prompts, responses, logs, and training data are kept, why, and how they are securely deleted, in line with legal and business requirements
- D. The number of GPUs per training job

<details><summary>Show answer</summary>

**Answer: C**

Retention policies balance the need to keep data for operations, audits, and legal holds against privacy obligations and risk. Keeping data longer than necessary increases exposure.

</details>

#### Q497 · Domain 5 · Medium · Multiple Choice
A company with many AWS accounts wants all API activity related to its AI workloads logged to one central, tamper-resistant location for governance. What is the recommended approach?

- A. Let each team decide whether to log.
- B. Store the logs on developers' laptops.
- C. Disable logging in production accounts.
- D. Create an AWS CloudTrail organization trail that delivers logs from all accounts to a central, access-restricted S3 bucket.

<details><summary>Show answer</summary>

**Answer: D**

An organization trail captures activity across every member account and centralizes the logs. With restricted access, and optionally S3 Object Lock, the logs become reliable audit evidence.

</details>

#### Q498 · Domain 5 · Medium · Multiple Choice
A government agency requires that all of its data remain within its home country. What is the most fundamental step when deploying an AI workload on AWS?

- A. Choose the Region with the lowest price, wherever it is located.
- B. Deploy resources and store data only in AWS Regions located within the required jurisdiction, and avoid features that route data elsewhere.
- C. Use Amazon CloudFront for all storage.
- D. Rely on employees to remember the policy.

<details><summary>Show answer</summary>

**Answer: B**

Customers choose where their data and workloads live by selecting Regions. Meeting residency requirements also means reviewing cross-Region features, backups, and replication settings.

</details>

#### Q499 · Domain 5 · Medium · Multiple Choice
An operations team wants dashboards and alarms for its Amazon Bedrock usage, covering invocation counts, latency, throttling, and token counts. Which service fits?

- A. Amazon CloudWatch metrics and alarms
- B. AWS Artifact
- C. Amazon Translate
- D. AWS Snowball

<details><summary>Show answer</summary>

**Answer: A**

Bedrock publishes runtime metrics to CloudWatch, which supports dashboards and alarms for performance, capacity, and cost signals. Monitoring and observation are part of the data governance strategies in the exam guide.

</details>

#### Q500 · Domain 5 · Hard · Multiple Choice
What is the purpose of the AWS **Generative AI Security Scoping Matrix**?

- A. To rank foundation models by accuracy
- B. To calculate token pricing
- C. To classify generative AI use cases by how much ownership and control the organization has (from using consumer apps to training its own models), which helps determine the relevant security and governance considerations
- D. To generate embeddings

<details><summary>Show answer</summary>

**Answer: C**

The matrix defines five scopes: (1) consumer apps, (2) enterprise apps, (3) pre-trained models, (4) fine-tuned models, and (5) self-trained models. As the scope number rises, the organization takes on more responsibility for security, data, and governance.

</details>

#### Q501 · Domain 5 · Hard · Multiple Choice
A company fine-tunes an Amazon Nova model in Amazon Bedrock with its proprietary data, and then serves the custom model in its own application. Which scope of the Generative AI Security Scoping Matrix applies?

- A. Scope 1: Consumer app
- B. Scope 2: Enterprise app
- C. Scope 3: Pre-trained models
- D. Scope 4: Fine-tuned models

<details><summary>Show answer</summary>

**Answer: D**

Customizing an existing FM with your own data is Scope 4. The organization takes on responsibility for its training data, the customized model, and that model's access controls, in addition to the application-level concerns of Scope 3.

</details>

#### Q502 · Domain 5 · Hard · Matching
Match each scenario to its Generative AI Security Scoping Matrix scope.

| Scenario | Scope |
|---|---|
| 1. An employee uses a public consumer chatbot website | a. Scope 1: Consumer app |
| 2. A company uses a SaaS business application with built-in GenAI features | b. Scope 2: Enterprise app |
| 3. A company builds its own app on an unmodified FM through Amazon Bedrock | c. Scope 3: Pre-trained models |
| 4. A company trains its own model from scratch | d. Scope 5: Self-trained models |

- A. 1-b, 2-a, 3-c, 4-d
- B. 1-a, 2-b, 3-c, 4-d
- C. 1-a, 2-c, 3-b, 4-d
- D. 1-a, 2-b, 3-d, 4-c

<details><summary>Show answer</summary>

**Answer: B**

The scopes run from the least control (consumer apps) to the most (self-trained models). Identifying the scope tells you which risks you own, such as data handling, model security, and output governance.

</details>

#### Q503 · Domain 5 · Medium · Multiple Choice
Employees have started pasting confidential source code into public AI chatbots. What governance measure should the company establish first?

- A. A generative AI acceptable use policy that defines approved tools, prohibited data types, and required practices, communicated with training
- B. A higher temperature setting
- C. A larger context window
- D. A ban on all computers

<details><summary>Show answer</summary>

**Answer: A**

Clear policies define what is allowed, such as which tools and data classifications may be used. Training and technical controls, such as approved enterprise tools and data loss prevention, then reinforce the policy.

</details>

#### Q504 · Domain 5 · Medium · Multiple Choice
A company deployed several production AI models two years ago and hasn't reviewed them since. Which governance practice is missing?

- A. Higher token limits
- B. Larger instances
- C. A defined review cadence: periodic reviews of model performance, risks, compliance, and continued business fit
- D. More few-shot examples

<details><summary>Show answer</summary>

**Answer: C**

Governance protocols should set how often models are reviewed, for example quarterly, and what triggers an ad-hoc review, such as regulation changes, incidents, or drift. Models and their contexts change over time.

</details>

#### Q505 · Domain 5 · Medium · Multiple Choice
Before launching a high-impact AI system, which review strategy best reflects good governance?

- A. A single developer approves their own work.
- B. No review is needed if the model is accurate.
- C. Only the marketing team reviews the system.
- D. A cross-functional review covering technical performance, security, legal and compliance, and ethical and responsible AI risks, with documented sign-off.

<details><summary>Show answer</summary>

**Answer: D**

High-impact AI affects many dimensions at once. Multidisciplinary reviews with documented approvals reduce blind spots and create accountability.

</details>

#### Q506 · Domain 5 · Medium · Multiple Choice
A company is rolling out GenAI tools to 5,000 employees. Which governance requirement helps ensure that the tools are used safely?

- A. Disabling all logging
- B. Mandatory training on approved use, data handling rules, recognizing hallucinations, and how to report issues
- C. Allowing any data to be entered into any tool
- D. Keeping the AI policy secret

<details><summary>Show answer</summary>

**Answer: B**

Team training requirements are part of governance protocols. Policies work only when people understand them and know how to follow them.

</details>

#### Q507 · Domain 5 · Medium · Multiple Choice
Which practice reflects a **transparency standard** within an AI governance program?

- A. Requiring documentation, such as model cards, for every production model, and disclosing AI use to affected users
- B. Hiding which models are in use
- C. Keeping no records of model versions
- D. Removing citations from RAG answers

<details><summary>Show answer</summary>

**Answer: A**

Transparency standards define what must be documented and disclosed, and to whom. This makes AI use visible to stakeholders, auditors, and users.

</details>

#### Q508 · Domain 5 · Medium · Multiple Choice
A company's policy requires that all SageMaker AI endpoint configurations use KMS encryption. How can it automatically detect configurations that don't comply?

- A. Amazon Polly
- B. Amazon Translate
- C. An AWS Config rule that evaluates SageMaker AI endpoint configurations for KMS encryption
- D. Manual quarterly spreadsheet reviews only

<details><summary>Show answer</summary>

**Answer: C**

AWS Config rules, including managed rules for SageMaker AI, continuously evaluate resources against policies and flag non-compliant ones. They can also trigger automated remediation.

</details>

#### Q509 · Domain 5 · Hard · Multiple Choice
Which statement correctly distinguishes AWS CloudTrail from Amazon CloudWatch?

- A. They are the same service with different names.
- B. CloudTrail records API activity (who did what, and when) for auditing; CloudWatch collects metrics and logs, and provides alarms for operational monitoring.
- C. CloudWatch records only API calls; CloudTrail tracks only CPU usage.
- D. Neither can be used with AI services.

<details><summary>Show answer</summary>

**Answer: B**

CloudTrail is about governance and audit (account activity). CloudWatch is about performance and operational health (metrics, logs, alarms). Exam questions often test this distinction.

</details>

#### Q510 · Domain 5 · Medium · Multiple Choice
A company wants to assess its use of Amazon Bedrock and SageMaker AI against generative AI best-practice controls, with evidence collected automatically. Which approach fits?

- A. Amazon Polly
- B. AWS Snowball
- C. Amazon Lex
- D. AWS Audit Manager with its prebuilt generative AI best practices framework

<details><summary>Show answer</summary>

**Answer: D**

Audit Manager includes a prebuilt framework for generative AI best practices. It maps controls to evidence that is collected automatically from AWS services, which simplifies governance assessments.

</details>

#### Q511 · Domain 5 · Hard · Multiple Choice
A company connects a RAG assistant to its entire document repository, ignoring the repository's existing permissions. Junior staff can now get answers drawn from executive compensation files. What governance failure occurred, and what is the fix?

- A. Oversharing caused by ignoring source permissions; enforce document-level access controls during retrieval, so users only receive content they are authorized to see.
- B. Model hallucination; lower the temperature.
- C. A small context window; use a bigger model.
- D. Slow retrieval; add more GPUs.

<details><summary>Show answer</summary>

**Answer: A**

GenAI assistants can expose data far faster than manual search. Data governance must carry existing access controls into retrieval, for example through permission-aware connectors, metadata filters, or separate indexes.

</details>

#### Q512 · Domain 5 · Medium · Multiple Choice
An ML governance team wants a single view of all deployed SageMaker AI models, including their monitoring status, model cards, and endpoint health. Which feature fits?

- A. Amazon Polly
- B. AWS Snowball
- C. Amazon SageMaker Model Dashboard
- D. Amazon Translate

<details><summary>Show answer</summary>

**Answer: C**

SageMaker Model Dashboard provides a centralized portfolio view of models, showing monitoring results and governance information, so that teams can spot issues across many models.

</details>

#### Q513 · Domain 5 · Medium · Multiple Choice
A company wants business and data teams to discover, request access to, and share governed data assets for analytics and ML through a catalog with built-in approval workflows. Which service fits?

- A. Amazon Polly
- B. Amazon DataZone (the catalog capability in Amazon SageMaker)
- C. AWS Snowball
- D. Amazon Lex

<details><summary>Show answer</summary>

**Answer: B**

Amazon DataZone, which powers the catalog in Amazon SageMaker Unified Studio, provides a business data catalog with publishing, subscription, and approval workflows. It supports governed data sharing across teams.

</details>

#### Q514 · Domain 5 · Easy · True/False
True or False: Under the shared responsibility model, customers are responsible for classifying their data and configuring access controls for their AI workloads.

- A. True
- B. False

<details><summary>Show answer</summary>

**Answer: A (True)**

Data classification, IAM configuration, and decisions about which data is used with which services are customer responsibilities. AWS provides the tools, but customers decide how to use them.

</details>

#### Q515 · Domain 5 · Medium · Ordering
Put these steps for establishing an AI governance program in a logical order:

1. Monitor and audit AI systems
2. Define AI policies and risk appetite
3. Train teams on the policies
4. Implement technical controls
5. Review and update the program periodically

- A. 2 → 4 → 3 → 5 → 1
- B. 3 → 2 → 4 → 1 → 5
- C. 2 → 3 → 4 → 1 → 5
- D. 4 → 2 → 3 → 1 → 5

<details><summary>Show answer</summary>

**Answer: C**

Governance starts with policies, which are then communicated through training and enforced with controls. Ongoing monitoring and audits generate evidence, and periodic reviews update the program as risks and regulations change.

</details>

#### Q516 · Domain 5 · Medium · Multiple Response
A company is preparing for an external audit of its AI platform. Which TWO AWS services most directly provide audit evidence? (Select TWO.)

- A. Amazon Polly
- B. AWS Audit Manager
- C. Amazon Translate
- D. AWS CloudTrail
- E. Amazon Rekognition

<details><summary>Show answer</summary>

**Answer: B, D**

Audit Manager collects and organizes evidence against control frameworks, and CloudTrail provides an authoritative record of account activity. Polly, Translate, and Rekognition are AI services, not audit tools.

</details>

#### Q517 · Domain 5 · Medium · Multiple Choice
Data quality problems in an ML pipeline keep going unresolved because no one is clearly responsible for each dataset. Which data governance practice addresses this?

- A. Increasing the model size
- B. Disabling monitoring
- C. Raising the temperature
- D. Assigning data owners and data stewards who are accountable for each dataset's quality, access, and lifecycle

<details><summary>Show answer</summary>

**Answer: D**

Clear ownership and stewardship roles create accountability for data quality, access approvals, and retention decisions. They are a foundation of effective data governance.

</details>

#### Q518 · Domain 5 · Medium · Multiple Choice
Before approving a new third-party foundation model for enterprise use, what should the governance team evaluate?

- A. The provider's terms for data usage and retention, licensing restrictions, indemnification, security posture, and the model's documentation of limitations
- B. Only the model's logo
- C. Only the model's release date
- D. Nothing, if the model is popular

<details><summary>Show answer</summary>

**Answer: A**

Third-party model risk assessments cover legal, security, privacy, and responsible AI factors. Model or service cards and provider agreements are key inputs.

</details>

#### Q519 · Domain 5 · Hard · Multiple Choice
A customer-facing chatbot suddenly starts producing harmful responses after a prompt-template change. What should a mature AI governance program already have in place?

- A. Nothing; incidents can't be planned for.
- B. An AI incident response plan that defines detection, escalation, rollback (for example, reverting to the previous prompt version), communication, and post-incident review
- C. A policy to delete all logs during incidents
- D. A rule that only the model can decide how to respond

<details><summary>Show answer</summary>

**Answer: B**

AI-specific incident response, supported by versioned prompts and models, monitoring, and clear ownership, limits harm and speeds recovery. Post-incident reviews feed improvements back into the controls.

</details>

#### Q520 · Domain 5 · Medium · Multiple Choice
After launch, how should a company monitor whether its GenAI application continues to meet governance and quality requirements?

- A. Check it only once at launch.
- B. Rely on anecdotal complaints only.
- C. Continuously track quality indicators, such as guardrail interventions, user feedback, and evaluation scores, alongside cost and usage metrics, and alert on anomalies.
- D. Disable metrics to save money.

<details><summary>Show answer</summary>

**Answer: C**

Observation and monitoring are part of the data governance strategies in the exam guide. Ongoing signals reveal drift, misuse, and quality degradation early.

</details>

#### Q521 · Domain 5 · Hard · Multiple Choice
A regulated bank must prove to examiners that only its approved foundation models can be used, and that any attempt to use other models is detected. Which combination best meets this requirement?

- A. Ask teams to self-report the models they use each year.
- B. Use Bedrock playgrounds only.
- C. Use a higher temperature for unapproved models.
- D. Use SCPs and IAM policies to deny unapproved model invocations, and AWS CloudTrail (with AWS Config where applicable) to record activity and provide evidence.

<details><summary>Show answer</summary>

**Answer: D**

Preventive controls, such as SCPs and IAM, enforce the policy. Detective controls, such as CloudTrail and Config, record activity and produce evidence. Together, they demonstrate effective governance to examiners.

</details>

#### Q522 · Domain 5 · Medium · Multiple Choice
An organization's AI governance framework classifies loan denials and medical triage as high-risk decisions. Which policy is most appropriate for these use cases?

- A. Require meaningful human oversight and review before final decisions, with documented accountability.
- B. Fully automate them, with no human involvement.
- C. Use the most creative model settings.
- D. Avoid documenting decisions.

<details><summary>Show answer</summary>

**Answer: A**

Risk-based governance applies stronger controls to higher-impact uses. Human-in-the-loop review, for example through Amazon A2I, together with documentation, supports fairness, accuracy, and accountability.

</details>

#### Q523 · Domain 5 · Medium · Multiple Choice
A healthcare startup needs to review and accept the AWS Business Associate Addendum (BAA) before processing PHI. Where does it do this?

- A. Amazon Polly
- B. Amazon SageMaker Canvas
- C. AWS Artifact (Agreements)
- D. Amazon Lex

<details><summary>Show answer</summary>

**Answer: C**

AWS Artifact provides both compliance reports and agreements. Customers can review and accept agreements such as the BAA there, for their account or organization.

</details>

#### Q524 · Domain 5 · Hard · Multiple Choice
An auditor asks two questions: (1) "Who changed the guardrail configuration last Tuesday?" and (2) "What exact prompt did a user send and what did the model reply?" Which sources answer these questions?

- A. CloudWatch metrics for both
- B. AWS CloudTrail for (1); Amazon Bedrock model invocation logging for (2)
- C. AWS Artifact for both
- D. Amazon Inspector for (1); AWS Trusted Advisor for (2)

<details><summary>Show answer</summary>

**Answer: B**

CloudTrail records management activity, such as who updated a guardrail and when. Model invocation logging captures the content of requests and responses. CloudTrail does not capture full prompt and response text.

</details>

#### Q525 · Domain 5 · Hard · Multiple Choice
A healthcare company is building a patient-support assistant on Amazon Bedrock with a knowledge base of clinical guidance documents. Which design best addresses security, compliance, and governance together?

- A. Use a public S3 bucket for documents, disable logging, and rely on the system prompt for privacy.
- B. Use any Region and any model, and handle compliance later.
- C. Let the LLM decide which patient records each user may view.
- D. Accept a BAA and use HIPAA-eligible services; encrypt data with KMS; connect through PrivateLink; enforce least-privilege IAM and user authentication; apply Guardrails with PII filters and contextual grounding checks; enable CloudTrail and protected invocation logging; and document the model in a model card with a defined review cadence.

<details><summary>Show answer</summary>

**Answer: D**

This option layers compliance (BAA, eligible services), data protection (encryption, private connectivity), access control (IAM, authentication), safety (Guardrails), auditability (CloudTrail, logging), and governance (documentation, reviews). The other options violate basic security and governance principles.

</details>

---

## Coverage Summary and Self-Verification

### Questions per domain

| Domain | Range | Questions | Official exam weight |
|---|---|---|---|
| 1. Fundamentals of AI and ML | Q1–Q105 | 105 | 20% |
| 2. Fundamentals of Generative AI | Q106–Q210 | 105 | 24% |
| 3. Applications of Foundation Models | Q211–Q315 | 105 | 28% |
| 4. Guidelines for Responsible AI | Q316–Q420 | 105 | 14% |
| 5. Security, Compliance, and Governance | Q421–Q525 | 105 | 14% |
| **Total** | | **525** | |

### Difficulty mix

| Domain | Easy | Medium | Hard |
|---|---|---|---|
| Domain 1 | 31 | 59 | 15 |
| Domain 2 | 33 | 51 | 21 |
| Domain 3 | 17 | 58 | 30 |
| Domain 4 | 18 | 57 | 30 |
| Domain 5 | 14 | 66 | 25 |
| **Total** | **113 (21.5%)** | **291 (55.4%)** | **121 (23.0%)** |

### Question-type mix

| Domain | Multiple Choice | Multiple Response | True/False | Matching | Ordering |
|---|---|---|---|---|---|
| Domain 1 | 94 | 4 | 4 | 2 | 1 |
| Domain 2 | 94 | 4 | 4 | 2 | 1 |
| Domain 3 | 92 | 4 | 4 | 2 | 3 |
| Domain 4 | 92 | 6 | 5 | 2 | 0 |
| Domain 5 | 91 | 4 | 5 | 3 | 2 |
| **Total** | **463** | **22** | **22** | **11** | **7** |

### Self-verification checklist

| Check | Result |
|---|---|
| 1. More than 500 original questions | ✅ 525 questions |
| 2. Distributed across all five domains | ✅ 105 per domain, evenly split as requested |
| 3. Every question has a correct answer and a detailed explanation | ✅ Each answer block states the correct option and explains why it is right, and usually why the distractors are wrong |
| 4. Variety of question types and difficulties | ✅ 5 question types; Easy, Medium, and Hard levels in every domain |
| 5. Clear organization and navigation | ✅ Table of contents, per-domain task indexes, consistent tags (number · domain · difficulty · type), and collapsible answers |

### Suggested study plan using this bank

1. **Baseline:** Take 13 questions from each domain (65 total, the length of the real exam) and score yourself.
2. **Weight your review:** The real exam weights Domain 3 most heavily (28%), followed by Domain 2 (24%). Spend proportionally more time there, even though this bank splits questions evenly.
3. **Target weak tasks:** Use the task indexes to drill the specific task statements where you scored lowest.
4. **Read every explanation:** Many explanations name the correct service and also say why look-alike services are wrong. Telling similar services apart is the most common source of mistakes on this exam.
5. **Final pass:** Reattempt only the Hard questions in the 48 hours before your exam.
