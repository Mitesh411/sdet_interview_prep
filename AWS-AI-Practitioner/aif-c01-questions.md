# AWS Certified AI Practitioner (AIF-C01): Exam-Style Questions

> **Last reviewed:** 2026-11-13 against the AIF-C01 exam guide (v1.4) · AI-assisted structural and staleness review · see [review-log.md](review-log.md)
>
> **Format:** 57 exam-style questions · single answer unless marked **(Select TWO.)** · each tagged with its exam domain
> **Answers:** Each answer is directly below its question inside a collapsible **"Show answer"** block, with an explanation. If your Markdown viewer doesn't support collapsible blocks, the answers will show as plain text, so cover them while you practise.
> **Source:** These questions are collected exam-style practice material. They are not original to this repository, and they are not confirmed real exam questions.

| Domain | Questions |
|---|---|
| 1. Fundamentals of AI and ML | 17 |
| 2. Fundamentals of Generative AI | 11 |
| 3. Applications of Foundation Models | 12 |
| 4. Guidelines for Responsible AI | 8 |
| 5. Security, Compliance, and Governance | 9 |
| **Total** | **57** |

---

## Questions

### Q1
*Domain 5: Security, Compliance, and Governance · Multiple Choice*

An AI practitioner trained a custom model on Amazon Bedrock by using a training dataset that contains confidential data. The AI practitioner wants to ensure that the custom model does not generate inference responses based on confidential data. How should the AI practitioner prevent responses based on confidential data?

- A. Delete the custom model. Remove the confidential data from the training dataset. Retrain the custom model.
- B. Mask the confidential data in the inference responses by using dynamic data masking.
- C. Encrypt the confidential data in the inference responses by using Amazon SageMaker.
- D. Encrypt the confidential data in the custom model by using AWS Key Management Service (AWS KMS).

<details><summary>Show answer</summary>

**Answer: A**

A model can't "forget" data it was trained on. Masking or encrypting the outputs doesn't stop the model from having learned the confidential content. The only reliable fix is to remove the data from the training set and train a new custom model.

</details>

### Q2
*Domain 3: Applications of Foundation Models · Multiple Choice*

Which feature of Amazon OpenSearch Service gives companies the ability to build vector database applications?

- A. Integration with Amazon S3 for object storage.
- B. Support for geospatial indexing and queries.
- C. Scalable index management and nearest neighbor search capability.
- D. Ability to perform real-time analysis on streaming data.

<details><summary>Show answer</summary>

**Answer: C**

OpenSearch Service supports vector search through its k-nearest neighbor (k-NN) capability with scalable indexes, which is what a vector database needs. S3 integration, geospatial queries and streaming analytics aren't vector features.

</details>

### Q3
*Domain 2: Fundamentals of Generative AI · Multiple Choice*

A company wants to display the total sales for its top-selling products across various retail locations in the past 12 months. Which AWS solution should the company use to automate the generation of graphs?

- A. Amazon Q in Amazon EC2.
- B. Amazon Q Developer.
- C. Amazon Q in Amazon QuickSight.
- D. Amazon Q in AWS Chatbot.

<details><summary>Show answer</summary>

**Answer: C**

Amazon Q in QuickSight generates visuals and dashboards from natural-language requests, so it fits a business intelligence (BI) charting requirement. Amazon Q Developer is for software development. AWS Chatbot is now called Amazon Q Developer in chat applications and is for ChatOps.

</details>

### Q4
*Domain 4: Guidelines for Responsible AI · Multiple Choice*

A company wants to build an interactive application for children that generates new stories based on classic stories. The company wants to use Amazon Bedrock and needs to ensure that the results and topics are appropriate for children. Which AWS service or feature will meet these requirements?

- A. Amazon Rekognition.
- B. Amazon Bedrock playgrounds.
- C. Amazon Bedrock Guardrails.
- D. Amazon Bedrock Agents.

<details><summary>Show answer</summary>

**Answer: C**

Amazon Bedrock Guardrails (formerly Guardrails for Amazon Bedrock) applies content filters and denied topics to both prompts and responses, which keeps output age-appropriate. Rekognition analyzes images, playgrounds are for experimenting, and Agents run multi-step tasks.

</details>

### Q5
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company has developed an ML model for image classification. The company wants to deploy the model to production so that a web application can use the model. The company needs to implement a solution to host the model and serve predictions without managing any of the underlying infrastructure. Which solution will meet these requirements?

- A. Use Amazon SageMaker Serverless Inference to deploy the model.
- B. Use Amazon CloudFront to deploy the model.
- C. Use Amazon API Gateway to host the model and serve predictions.
- D. Use AWS Batch to host the model and serve predictions.

<details><summary>Show answer</summary>

**Answer: A**

SageMaker Serverless Inference hosts a model and scales compute automatically (down to zero), so there's no infrastructure to manage. CloudFront is a CDN, API Gateway fronts APIs but doesn't host models, and AWS Batch is for batch jobs.

</details>

### Q6
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company has petabytes of unlabeled customer data to use for an advertisement campaign. The company wants to classify its customers into tiers to advertise and promote the company’s products. Which methodology should the company use to meet these requirements?

- A. Supervised learning.
- B. Unsupervised learning.
- C. Reinforcement learning.
- D. Reinforcement learning from human feedback (RLHF).

<details><summary>Show answer</summary>

**Answer: B**

The data is unlabeled and the goal is to find natural groupings (tiers), which is clustering, a form of unsupervised learning. Supervised learning needs labels. RL and RLHF learn from rewards or human feedback.

</details>

### Q7
*Domain 4: Guidelines for Responsible AI · Multiple Choice*

A company makes forecasts each quarter to decide how to optimize operations to meet expected demand. The company uses ML models to make these forecasts. An AI practitioner is writing a report about the trained ML models to provide transparency and explainability to company stakeholders. What should the AI practitioner include in the report to meet the transparency and explainability requirements?

- A. Code for model training.
- B. Partial dependence plots (PDPs).
- C. Sample data for training.
- D. Model convergence tables.

<details><summary>Show answer</summary>

**Answer: B**

Partial dependence plots show how each input feature affects the model's predictions, which explains model behavior to non-technical stakeholders. Training code, sample data and convergence tables don't explain why the model predicts what it does.

</details>

### Q8
*Domain 2: Fundamentals of Generative AI · Multiple Choice*

Which option is a use case for generative AI models?

- A. Improving network security by using intrusion detection systems.
- B. Creating photorealistic images from text descriptions for digital marketing.
- C. Enhancing database performance by using optimized indexing.
- D. Analyzing financial data to forecast stock market trends.

<details><summary>Show answer</summary>

**Answer: B**

Generating new content (here, images from text prompts) is the defining use of generative AI. Intrusion detection, index tuning and forecasting are traditional ML or database tasks.

</details>

### Q9
*Domain 2: Fundamentals of Generative AI · Multiple Choice*

An AI practitioner is using a large language model (LLM) to create content for marketing campaigns. The generated content sounds plausible and factual but is incorrect. Which problem is the LLM having?

- A. Data leakage.
- B. Hallucination.
- C. Overfitting.
- D. Underfitting.

<details><summary>Show answer</summary>

**Answer: B**

A hallucination is output that sounds confident and plausible but is factually wrong. Overfitting and underfitting describe how a model generalizes from training data, and data leakage is a flaw in how training and test data are split.

</details>

### Q10
*Domain 4: Guidelines for Responsible AI · Multiple Response*

A loan company is building a generative AI-based solution to offer new applicants discounts based on specific business criteria. The company wants to build and use an AI model responsibly to minimize bias that could negatively affect some customers. Which actions should the company take to meet these requirements? (Select TWO.)

- A. Detect imbalances or disparities in the data.
- B. Ensure that the model runs frequently.
- C. Evaluate the model’s behavior so that the company can provide transparency to stakeholders.
- D. Use the Recall-Oriented Understudy for Gisting Evaluation (ROUGE) technique to ensure that the model is 100% accurate.
- E. Ensure that the model’s inference time is within the accepted limits.

<details><summary>Show answer</summary>

**Answer: A, C**

Responsible AI starts with finding imbalances in the training data and continues with evaluating model behavior so you can be transparent about it. How often the model runs and its latency don't address bias, and ROUGE measures summary overlap, not "100% accuracy".

</details>

### Q11
*Domain 4: Guidelines for Responsible AI · Multiple Choice*

A medical company is customizing a foundation model (FM) for diagnostic purposes. The company needs the model to be transparent and explainable to meet regulatory requirements. Which solution will meet these requirements?

- A. Configure the security and compliance by using Amazon Inspector.
- B. Generate simple metrics, reports, and examples by using Amazon SageMaker Clarify.
- C. Encrypt and secure training data by using Amazon Macie.
- D. Gather more data. Use Amazon Rekognition to add custom labels to the data.

<details><summary>Show answer</summary>

**Answer: B**

SageMaker Clarify produces bias metrics and feature-attribution (explainability) reports, which supports regulatory transparency. Inspector scans for vulnerabilities, Macie finds sensitive data, and Rekognition custom labels don't add explainability.

</details>

### Q12
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company is building a solution to generate images for protective eyewear. The solution must have high accuracy and must minimize the risk of incorrect annotations. Which solution will meet these requirements?

- A. Human-in-the-loop validation by using Amazon SageMaker Ground Truth Plus.
- B. Data augmentation by using an Amazon Bedrock knowledge base.
- C. Image recognition by using Amazon Rekognition.
- D. Data summarization by using Amazon QuickSight.

<details><summary>Show answer</summary>

**Answer: A**

SageMaker Ground Truth Plus is a managed labeling service with expert human reviewers, so it reduces annotation errors. Knowledge bases provide RAG context, Rekognition analyzes images, and QuickSight is for BI.

</details>

### Q13
*Domain 5: Security, Compliance, and Governance · Multiple Choice*

A security company is using Amazon Bedrock to run foundation models (FMs). The company wants to ensure that only authorized users invoke the models. The company needs to identify any unauthorized access attempts to set appropriate AWS Identity and Access Management (IAM) policies and roles for future iterations of the FMs. Which AWS service should the company use to identify unauthorized users that are trying to access Amazon Bedrock?

- A. AWS Audit Manager.
- B. AWS CloudTrail.
- C. Amazon Fraud Detector.
- D. AWS Trusted Advisor.

<details><summary>Show answer</summary>

**Answer: B**

CloudTrail records every API call, including denied `InvokeModel` attempts, along with the caller's identity. That's what you need to spot unauthorized access. Audit Manager collects compliance evidence, Fraud Detector scores transactions, and Trusted Advisor gives best-practice checks.

</details>

### Q14
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company manually reviews all submitted resumes in PDF format. As the company grows, the company expects the volume of resumes to exceed the company’s review capacity. The company needs an automated system to convert the PDF resumes into plain text format for additional processing. Which AWS service meets this requirement?

- A. Amazon Textract.
- B. Amazon Personalize.
- C. Amazon Lex.
- D. Amazon Transcribe.

<details><summary>Show answer</summary>

**Answer: A**

Amazon Textract extracts text, forms and tables from scanned documents and PDFs. Personalize builds recommendations, Lex builds chatbots, and Transcribe converts speech to text.

</details>

### Q15
*Domain 3: Applications of Foundation Models · Multiple Choice*

A company wants to use large language models (LLMs) with Amazon Bedrock to develop a chat interface for the company’s product manuals. The manuals are stored as PDF files. Which solution meets these requirements MOST cost-effectively?

- A. Use prompt engineering to add one PDF file as context to the user prompt when the prompt is submitted to Amazon Bedrock.
- B. Use prompt engineering to add all the PDF files as context to the user prompt when the prompt is submitted to Amazon Bedrock.
- C. Use all the PDF documents to fine-tune a model with Amazon Bedrock. Use the fine-tuned model to process user prompts.
- D. Upload PDF documents to an Amazon Bedrock knowledge base. Use the knowledge base to provide context when users submit prompts to Amazon Bedrock.

<details><summary>Show answer</summary>

**Answer: D**

A Bedrock knowledge base uses RAG: it retrieves only the relevant chunks of the manuals for each question. Stuffing whole PDFs into every prompt costs more tokens (and may exceed the context window), and fine-tuning costs more and doesn't keep up with document changes.

</details>

### Q16
*Domain 2: Fundamentals of Generative AI · Multiple Choice*

Which term describes the numerical representations of real-world objects and concepts that AI and natural language processing (NLP) models use to improve understanding of textual information?

- A. Embeddings.
- B. Tokens.
- C. Models.
- D. Binaries.

<details><summary>Show answer</summary>

**Answer: A**

Embeddings are numeric vectors that capture meaning, so similar concepts sit close together. Tokens are the units of text a model reads and writes, not semantic representations.

</details>

### Q17
*Domain 2: Fundamentals of Generative AI · Multiple Choice*

A company is building an application that needs to generate synthetic data that is based on existing data. Which type of model can the company use to meet this requirement?

- A. Generative adversarial network (GAN).
- B. XGBoost.
- C. Residual neural network.
- D. WaveNet.

<details><summary>Show answer</summary>

**Answer: A**

A GAN's generator learns to produce new samples that its discriminator can't tell apart from real data, which makes it well suited to synthetic data. XGBoost is for classification and regression, ResNet is for image classification, and WaveNet generates audio.

</details>

### Q18
*Domain 2: Fundamentals of Generative AI · Multiple Choice*

A company wants to use generative AI to increase developer productivity and software development. The company wants to use Amazon Q Developer. What can Amazon Q Developer do to help the company meet these requirements?

- A. Create software snippets, reference tracking, and open-source license tracking.
- B. Run an application without provisioning or managing servers.
- C. Enable voice commands for coding and providing natural language search.
- D. Convert audio files to text documents by using ML models.

<details><summary>Show answer</summary>

**Answer: A**

Amazon Q Developer (formerly CodeWhisperer) generates code suggestions and flags suggestions that resemble open-source code, with reference and license tracking. Running apps without servers describes Lambda, and audio-to-text describes Transcribe.

</details>

### Q19
*Domain 2: Fundamentals of Generative AI · Multiple Choice*

A company wants to create an application by using Amazon Bedrock. The company has a limited budget and prefers flexibility without long-term commitment. Which Amazon Bedrock pricing model meets these requirements?

- A. On-Demand.
- B. Model customization.
- C. Provisioned Throughput.
- D. Spot Instance.

<details><summary>Show answer</summary>

**Answer: A**

On-Demand pricing charges per token with no commitment, which fits a limited budget that needs flexibility. Provisioned Throughput requires a time-based commitment, "model customization" is a training charge, and Spot Instances aren't a Bedrock pricing model.

</details>

### Q20
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A digital devices company wants to predict customer demand for memory hardware. The company does not have coding experience or knowledge of ML algorithms and needs to develop a data-driven predictive model. The company needs to perform analysis on internal data and external data. Which solution will meet these requirements?

- A. Store the data in Amazon S3. Create ML models and demand forecast predictions by using Amazon SageMaker built-in algorithms that use the data from Amazon S3.
- B. Import the data into Amazon SageMaker Data Wrangler. Create ML models and demand forecast predictions by using SageMaker built-in algorithms.
- C. Import the data into Amazon SageMaker Data Wrangler. Build ML models and demand forecast predictions by using an Amazon Personalize Trending-Now recipe.
- D. Import the data into Amazon SageMaker Canvas. Build ML models and demand forecast predictions by selecting the values in the data from SageMaker Canvas.

<details><summary>Show answer</summary>

**Answer: D**

SageMaker Canvas is a no-code, point-and-click ML tool that supports forecasting and imports from many data sources. Built-in algorithms and Data Wrangler workflows need ML knowledge, and Personalize recipes are for recommendations, not demand forecasting.

</details>

### Q21
*Domain 2: Fundamentals of Generative AI · Multiple Choice*

What are tokens in the context of generative AI models?

- A. Tokens are the basic units of input and output that a generative AI model operates on, representing words, subwords, or other linguistic units.
- B. Tokens are the mathematical representations of words or concepts used in generative AI models.
- C. Tokens are the pre-trained weights of a generative AI model that are fine-tuned for specific tasks.
- D. Tokens are the specific prompts or instructions given to a generative AI model to generate output.

<details><summary>Show answer</summary>

**Answer: A**

Tokens are the chunks of text (words, subwords or characters) that a model reads and generates. Option B describes embeddings, C describes model weights, and D describes prompts.

</details>

### Q22
*Domain 5: Security, Compliance, and Governance · Multiple Choice*

An AI practitioner is using an Amazon Bedrock base model to summarize session chats from the customer service department. The AI practitioner wants to store invocation logs to monitor model input and output data. Which strategy should the AI practitioner use?

- A. Configure AWS CloudTrail as the logs destination for the model.
- B. Enable invocation logging in Amazon Bedrock.
- C. Configure AWS Audit Manager as the logs destination for the model.
- D. Configure model invocation logging in Amazon EventBridge.

<details><summary>Show answer</summary>

**Answer: B**

Amazon Bedrock model invocation logging captures full request and response data (inputs and outputs) and sends it to CloudWatch Logs or S3. CloudTrail records API activity but not prompt and response content.

</details>

### Q23
*Domain 4: Guidelines for Responsible AI · Multiple Choice*

A company needs to build its own large language model (LLM) based on only the company’s private data. The company is concerned about the environmental effect of the training process. Which Amazon EC2 instance type has the LEAST environmental effect when training LLMs?

- A. Amazon EC2 C series.
- B. Amazon EC2 G series.
- C. Amazon EC2 P series.
- D. Amazon EC2 Trn series.

<details><summary>Show answer</summary>

**Answer: D**

AWS Trainium (Trn) instances are purpose-built for training and are more energy-efficient for training deep learning models than general-purpose GPU (G/P) or compute (C) instances. That makes them the more sustainable choice.

</details>

### Q24
*Domain 5: Security, Compliance, and Governance · Multiple Choice*

A financial institution is using Amazon Bedrock to develop an AI application. The application is hosted in a VPC. To meet regulatory compliance standards, the VPC is not allowed access to any internet traffic. Which AWS service or feature will meet these requirements?

- A. AWS PrivateLink.
- B. Amazon Macie.
- C. Amazon CloudFront.
- D. Internet gateway.

<details><summary>Show answer</summary>

**Answer: A**

AWS PrivateLink (an interface VPC endpoint) lets the VPC reach Amazon Bedrock privately, without an internet gateway or NAT. Macie discovers sensitive data, CloudFront is a public CDN, and an internet gateway would break the requirement.

</details>

### Q25
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company built a deep learning model for object detection and deployed the model to production. Which AI process occurs when the model analyzes a new image to identify objects?

- A. Training.
- B. Inference.
- C. Model deployment.
- D. Bias correction.

<details><summary>Show answer</summary>

**Answer: B**

Inference is using a trained model to make predictions on new data. Training is learning from data, and deployment is making the model available.

</details>

### Q26
*Domain 5: Security, Compliance, and Governance · Multiple Choice*

A company is using Amazon SageMaker Studio notebooks to build and train ML models. The company stores the data in an Amazon S3 bucket. The company needs to manage the flow of data from Amazon S3 to SageMaker Studio notebooks. Which solution will meet this requirement?

- A. Use Amazon Inspector to monitor SageMaker Studio.
- B. Use Amazon Macie to monitor SageMaker Studio.
- C. Configure SageMaker to use a VPC with an S3 endpoint.
- D. Configure SageMaker to use S3 Glacier Deep Archive.

<details><summary>Show answer</summary>

**Answer: C**

Running SageMaker Studio in a VPC with an S3 gateway endpoint keeps the data flow between S3 and the notebooks private and controllable through endpoint policies. Inspector and Macie don't control data flow, and Glacier Deep Archive is cold storage.

</details>

### Q27
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company is using domain-specific models. The company wants to avoid creating new models from the beginning. The company instead wants to adapt pre-trained models to create models for new, related tasks. Which ML strategy meets these requirements?

- A. Increase the number of epochs.
- B. Use transfer learning.
- C. Decrease the number of epochs.
- D. Use unsupervised learning.

<details><summary>Show answer</summary>

**Answer: B**

Transfer learning reuses a pre-trained model's learned knowledge and adapts it to a related task, so you avoid training from scratch. Changing the number of epochs doesn't change the strategy, and unsupervised learning is a different paradigm.

</details>

### Q28
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company wants to use AI to protect its application from threats. The AI solution needs to check if an IP address is from a suspicious source. Which solution meets these requirements?

- A. Build a speech recognition system.
- B. Create a natural language processing (NLP) named entity recognition system.
- C. Develop an anomaly detection system.
- D. Create a fraud forecasting system.

<details><summary>Show answer</summary>

**Answer: C**

Spotting suspicious IP addresses means finding behavior that deviates from normal patterns, which is anomaly detection. Speech recognition, named entity recognition (NER) and forecasting don't fit.

</details>

### Q29
*Domain 3: Applications of Foundation Models · Multiple Choice*

A company wants to use a large language model (LLM) to develop a conversational agent. The company needs to prevent the LLM from being manipulated with common prompt engineering techniques to perform undesirable actions or expose sensitive information. Which action will reduce these risks?

- A. Create a prompt template that teaches the LLM to detect attack patterns.
- B. Increase the temperature parameter on invocation requests to the LLM.
- C. Avoid using LLMs that are not listed in Amazon SageMaker.
- D. Decrease the number of input tokens on invocations of the LLM.

<details><summary>Show answer</summary>

**Answer: A**

A prompt template that defines expected behavior and teaches the model to recognize injection or jailbreak patterns reduces manipulation risk. Higher temperature only adds randomness, and limiting input tokens or the model catalog doesn't address prompt attacks.

</details>

### Q30
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company is developing a new model to predict the prices of specific items. The model performed well on the training dataset. When the company deployed the model to production, the model’s performance decreased significantly. What should the company do to mitigate this problem?

- A. Reduce the volume of data that is used in training.
- B. Add hyperparameters to the model.
- C. Increase the volume of data that is used in training.
- D. Increase the model training time.

<details><summary>Show answer</summary>

**Answer: C**

Good results on training data but poor results in production is overfitting. More, and more varied, training data helps the model generalize. Less data or longer training makes overfitting worse, and "adding hyperparameters" isn't a fix.

</details>

### Q31
*Domain 2: Fundamentals of Generative AI · Multiple Choice*

A law firm wants to build an AI application by using large language models (LLMs). The application will read legal documents and extract key points from the documents. Which solution meets these requirements?

- A. Build an automatic named entity recognition system.
- B. Create a recommendation engine.
- C. Develop a summarization chatbot.
- D. Develop a multi-language translation system.

<details><summary>Show answer</summary>

**Answer: C**

Extracting key points from long documents is summarization, a core LLM use case. NER pulls out entities rather than key points, and recommendation and translation solve different problems.

</details>

### Q32
*Domain 4: Guidelines for Responsible AI · Multiple Choice*

A company wants to classify human genes into 20 categories based on gene characteristics. The company needs an ML algorithm to document how the inner mechanism of the model affects the output. Which ML algorithm meets these requirements?

- A. Decision trees.
- B. Linear regression.
- C. Logistic regression.
- D. Neural networks.

<details><summary>Show answer</summary>

**Answer: A**

Decision trees are inherently interpretable: you can follow each split to see exactly how the inputs lead to the output, and they handle multi-class problems. Neural networks are black boxes, and linear and logistic regression don't naturally fit a 20-class problem this transparently.

</details>

### Q33
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company has built an image classification model to predict plant diseases from photos of plant leaves. The company wants to evaluate how many images the model classified correctly. Which evaluation metric should the company use to measure the model's performance?

- A. R-squared score.
- B. Accuracy.
- C. Root mean squared error (RMSE).
- D. Learning rate.

<details><summary>Show answer</summary>

**Answer: B**

Accuracy is the share of predictions that are correct, which is exactly what was asked. R-squared and RMSE are regression metrics, and learning rate is a hyperparameter, not a metric.

</details>

### Q34
*Domain 3: Applications of Foundation Models · Multiple Choice*

A company is using a pre-trained large language model (LLM) to build a chatbot for product recommendations. The company needs the LLM outputs to be short and written in a specific language. Which solution will align the LLM response quality with the company's expectations?

- A. Adjust the prompt.
- B. Choose an LLM of a different size.
- C. Increase the temperature.
- D. Increase the Top K value.

<details><summary>Show answer</summary>

**Answer: A**

Length and language are formatting requirements that are best handled with prompt instructions. It's the cheapest and fastest lever. A different model size doesn't guarantee format, and higher temperature or Top K makes output less predictable.

</details>

### Q35
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company uses Amazon SageMaker for its ML pipeline in a production environment. The company has large input data sizes up to 1 GB and processing times up to 1 hour. The company needs near real-time latency. Which SageMaker inference option meets these requirements?

- A. Real-time inference.
- B. Serverless inference.
- C. Asynchronous inference.
- D. Batch transform.

<details><summary>Show answer</summary>

**Answer: C**

Asynchronous inference queues requests, supports payloads up to 1 GB and processing up to 1 hour, and returns results in near real time. Real-time and serverless inference have much smaller payload and time limits, and batch transform isn't near real time.

</details>

### Q36
*Domain 5: Security, Compliance, and Governance · Multiple Choice*

A company wants to create a chatbot by using a foundation model (FM) on Amazon Bedrock. The FM needs to access encrypted data that is stored in an Amazon S3 bucket. The data is encrypted with Amazon S3 managed keys (SSE-S3). The FM encounters a failure when attempting to access the S3 bucket data. Which solution will meet these requirements?

- A. Ensure that the role that Amazon Bedrock assumes has permission to decrypt data with the correct encryption key.
- B. Set the access permissions for the S3 buckets to allow public access to enable access over the internet.
- C. Use prompt engineering techniques to tell the model to look for information in Amazon S3.
- D. Ensure that the S3 data does not contain sensitive information.

<details><summary>Show answer</summary>

**Answer: A**

The service role that Bedrock assumes needs IAM permission to read the bucket and, when objects are encrypted with KMS keys, to decrypt them. Making the bucket public is a security violation, and prompts can't grant permissions.

</details>

### Q37
*Domain 3: Applications of Foundation Models · Multiple Choice*

A company wants to use language models to create an application for inference on edge devices. The inference must have the lowest latency possible. Which solution will meet these requirements?

- A. Deploy optimized small language models (SLMs) on edge devices.
- B. Deploy optimized large language models (LLMs) on edge devices.
- C. Incorporate a centralized small language model (SLM) API for asynchronous communication with edge devices.
- D. Incorporate a centralized large language model (LLM) API for asynchronous communication with edge devices.

<details><summary>Show answer</summary>

**Answer: A**

Small language models need less compute and memory, so they run efficiently on the device itself. Running locally gives the lowest latency, with no network round trip. LLMs are too heavy for most edge hardware, and centralized APIs add network latency.

</details>

### Q38
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company wants to build an ML model by using Amazon SageMaker. The company needs to share and manage variables for model development across multiple teams. Which SageMaker feature meets these requirements?

- A. Amazon SageMaker Feature Store.
- B. Amazon SageMaker Data Wrangler.
- C. Amazon SageMaker Clarify.
- D. Amazon SageMaker Model Cards.

<details><summary>Show answer</summary>

**Answer: A**

SageMaker Feature Store is a central repository for storing, sharing and reusing ML features (variables) across teams. Data Wrangler prepares data, Clarify detects bias, and Model Cards document models.

</details>

### Q39
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company wants to develop an educational game where users answer questions such as the following: "A jar contains six red, four green, and three yellow marbles. What is the probability of choosing a green marble from the jar?" Which solution meets these requirements with the LEAST operational overhead?

- A. Use supervised learning to create a regression model that will predict probability.
- B. Use reinforcement learning to train a model to return the probability.
- C. Use code that will calculate probability by using simple rules and computations.
- D. Use unsupervised learning to create a model that will estimate probability density.

<details><summary>Show answer</summary>

**Answer: C**

The answer is a deterministic formula (4 green ÷ 13 total), so simple rule-based code is the most accurate option and has the least overhead. ML isn't appropriate when an exact rule exists.

</details>

### Q40
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

Which metric measures the runtime efficiency of operating AI models?

- A. Customer satisfaction score (CSAT).
- B. Training time for each epoch.
- C. Average response time.
- D. Number of training instances.

<details><summary>Show answer</summary>

**Answer: C**

Average response time (latency) measures how efficiently a deployed model serves requests at runtime. CSAT is a business metric, and epoch time and instance counts are training measures.

</details>

### Q41
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

A company is building a contact center application and wants to gain insights from customer conversations. The company wants to analyze and extract key information from the audio of the customer calls. Which solution meets these requirements?

- A. Build a conversational chatbot by using Amazon Lex.
- B. Transcribe call recordings by using Amazon Transcribe.
- C. Extract information from call recordings by using Amazon SageMaker Model Monitor.
- D. Create classification labels by using Amazon Comprehend.

<details><summary>Show answer</summary>

**Answer: B**

Amazon Transcribe converts call audio to text (and Call Analytics adds sentiment and issue detection), and the text can then be analyzed. Lex builds bots, Model Monitor watches model quality, and Comprehend works on text, not audio.

</details>

### Q42
*Domain 3: Applications of Foundation Models · Multiple Choice*

An AI practitioner wants to use a foundation model (FM) to design a search application. The search application must handle queries that have text and images. Which type of FM should the AI practitioner use to power the search application?

- A. Multi-modal embedding model.
- B. Text embedding model.
- C. Multi-modal generation model.
- D. Image generation model.

<details><summary>Show answer</summary>

**Answer: A**

Searching across text and images requires putting both into the same vector space, which is what a multimodal embedding model does. Text-only embeddings can't represent images, and generation models create content rather than enabling search.

</details>

### Q43
*Domain 3: Applications of Foundation Models · Multiple Choice*

A company uses a foundation model (FM) from Amazon Bedrock for an AI search tool. The company wants to fine-tune the model to be more accurate by using the company's data. Which strategy will successfully fine-tune the model?

- A. Provide labeled data with the prompt field and the completion field.
- B. Prepare the training dataset by creating a .txt file that contains multiple lines in .csv format.
- C. Purchase Provisioned Throughput for Amazon Bedrock.
- D. Train the model on journals and textbooks.

<details><summary>Show answer</summary>

**Answer: A**

Bedrock fine-tuning uses labeled examples in JSONL with `prompt` and `completion` fields, stored in S3. Provisioned Throughput is needed to run a custom model but doesn't fine-tune it, and unlabeled journals and textbooks are for continued pre-training, not fine-tuning.

</details>

### Q44
*Domain 1: Fundamentals of AI and ML · Multiple Choice*

An AI practitioner has a database of animal photos. The AI practitioner wants to automatically identify and categorize the animals in the photos without manual human effort. Which strategy meets these requirements?

- A. Object detection.
- B. Anomaly detection.
- C. Named entity recognition.
- D. Inpainting.

<details><summary>Show answer</summary>

**Answer: A**

Object detection (computer vision) finds and classifies objects in images automatically, for example with Amazon Rekognition. Anomaly detection, NER and inpainting don't classify the animals in photos.

</details>

### Q45
*Domain 5: Security, Compliance, and Governance · Multiple Choice*

How can companies use large language models (LLMs) securely on Amazon Bedrock?

- A. Design clear and specific prompts. Configure AWS Identity and Access Management (IAM) roles and policies by using least privilege access.
- B. Enable AWS Audit Manager for automatic model evaluation jobs.
- C. Enable Amazon Bedrock automatic model evaluation jobs.
- D. Use Amazon CloudWatch Logs to make models explainable and to monitor for bias.

<details><summary>Show answer</summary>

**Answer: A**

Clear, specific prompts reduce misuse, and least-privilege IAM policies control who can invoke which models. Audit Manager and automatic evaluations don't secure access, and CloudWatch Logs don't provide explainability or bias detection.

</details>

### Q46
*Domain 2: Fundamentals of Generative AI · Multiple Choice*

A company has terabytes of data in a database that the company can use for business analysis. The company wants to build an AI-based application that can build a SQL query from input text that employees provide. The employees have minimal experience with technology. Which solution meets these requirements?

- A. Generative pre-trained transformers (GPT).
- B. Residual neural network.
- C. Support vector machine.
- D. WaveNet.

<details><summary>Show answer</summary>

**Answer: A**

Generative pre-trained transformers understand natural language and can generate code such as SQL, so they're well suited to text-to-SQL. ResNet is for images, SVM is a classical classifier, and WaveNet generates audio.

</details>

### Q47
*Domain 4: Guidelines for Responsible AI · Multiple Choice*

An AI practitioner is building a model to generate images of humans in various professions. The AI practitioner discovered that the input data is biased and that specific attributes affect the image generation and create bias in the model. Which technique will solve the problem?

- A. Data augmentation for imbalanced classes.
- B. Model monitoring for class distribution.
- C. Retrieval Augmented Generation (RAG).
- D. Watermark detection for images.

<details><summary>Show answer</summary>

**Answer: A**

Bias from under-represented attributes is reduced by balancing the training data, for example by augmenting the under-represented classes. Monitoring detects drift but doesn't fix it, RAG supplies context to text models, and watermarking marks AI content.

</details>

### Q48
*Domain 3: Applications of Foundation Models · Multiple Choice*

A company is implementing the Amazon Titan foundation model (FM) by using Amazon Bedrock. The company needs to supplement the model by using relevant data from the company's private data sources. Which solution will meet this requirement?

- A. Use a different FM.
- B. Choose a lower temperature value.
- C. Create an Amazon Bedrock knowledge base.
- D. Enable model invocation logging.

<details><summary>Show answer</summary>

**Answer: C**

A Bedrock knowledge base adds RAG so the model can retrieve and use the company's private data at inference time. Switching models, lowering temperature or logging doesn't add private knowledge.

</details>

### Q49
*Domain 5: Security, Compliance, and Governance · Multiple Response*

A company wants to deploy a conversational chatbot to answer customer questions. The chatbot is based on a fine-tuned Amazon SageMaker JumpStart model. The application must comply with multiple regulatory frameworks. Which capabilities can the company show compliance for? (Select TWO.)

- A. Auto scaling inference endpoints.
- B. Threat detection.
- C. Data protection.
- D. Cost optimization.
- E. Loosely coupled microservices.

<details><summary>Show answer</summary>

**Answer: B, C**

Compliance frameworks are about security controls such as threat detection and data protection, and AWS provides attestations for these (for example GuardDuty and encryption). Auto scaling, cost and architecture style aren't compliance capabilities.

</details>

### Q50
*Domain 3: Applications of Foundation Models · Multiple Choice*

A company is training a foundation model (FM). The company wants to increase the accuracy of the model up to a specific acceptance level. Which solution will meet these requirements?

- A. Decrease the batch size.
- B. Increase the epochs.
- C. Decrease the epochs.
- D. Increase the temperature parameter.

<details><summary>Show answer</summary>

**Answer: B**

More epochs (full passes over the training data) let the model keep learning until it reaches the accuracy target, as long as you watch for overfitting. Fewer epochs reduce learning, and temperature is an inference setting, not a training setting.

</details>

### Q51
*Domain 3: Applications of Foundation Models · Multiple Choice*

A company is building a large language model (LLM) question answering chatbot. The company wants to decrease the number of actions call center employees need to take to respond to customer questions. Which business objective should the company use to evaluate the effect of the LLM chatbot?

- A. Website engagement rate.
- B. Average call duration.
- C. Corporate social responsibility.
- D. Regulatory compliance.

<details><summary>Show answer</summary>

**Answer: B**

Fewer steps for agents to answer a question shows up directly as shorter average call duration. Website engagement, CSR and compliance don't measure call-center efficiency.

</details>

### Q52
*Domain 4: Guidelines for Responsible AI · Multiple Choice*

Which functionality does Amazon SageMaker Clarify provide?

- A. Integrates a Retrieval Augmented Generation (RAG) workflow.
- B. Monitors the quality of ML models in production.
- C. Documents critical details about ML models.
- D. Identifies potential bias during data preparation.

<details><summary>Show answer</summary>

**Answer: D**

SageMaker Clarify detects bias in data during preparation (and in models after training) and explains predictions. Model Monitor watches production quality, Model Cards document models, and RAG is a Bedrock knowledge-base pattern.

</details>

### Q53
*Domain 1: Fundamentals of AI and ML · Multiple Response*

An ecommerce company wants to build a solution to determine customer sentiments based on written customer reviews of products. Which AWS services meet these requirements? (Select TWO.)

- A. Amazon Lex.
- B. Amazon Comprehend.
- C. Amazon Polly.
- D. Amazon Bedrock.
- E. Amazon Rekognition.

<details><summary>Show answer</summary>

**Answer: B, D**

Amazon Comprehend has built-in sentiment analysis for text, and an LLM on Amazon Bedrock can classify sentiment with a prompt. Lex builds chatbots, Polly converts text to speech, and Rekognition analyzes images.

</details>

### Q54
*Domain 3: Applications of Foundation Models · Multiple Choice*

A company has a foundation model (FM) that was customized by using Amazon Bedrock to answer customer queries about products. The company wants to validate the model's responses to new types of queries. The company needs to upload a new dataset that Amazon Bedrock can use for validation. Which AWS service meets these requirements?

- A. Amazon S3.
- B. Amazon Elastic Block Store (Amazon EBS).
- C. Amazon Elastic File System (Amazon EFS).
- D. AWS Snowcone.

<details><summary>Show answer</summary>

**Answer: A**

Amazon Bedrock reads training and validation datasets for model customization from Amazon S3. EBS and EFS are attached block and file storage, and Snowcone is an edge data-transfer device that has since been discontinued.

</details>

### Q55
*Domain 2: Fundamentals of Generative AI · Multiple Choice*

A company wants to assess the costs that are associated with using a large language model (LLM) to generate inferences. The company wants to use Amazon Bedrock to build generative AI applications. Which factor will drive the inference costs?

- A. Number of tokens consumed.
- B. Temperature value.
- C. Amount of data used to train the LLM.
- D. Total training time.

<details><summary>Show answer</summary>

**Answer: A**

Bedrock on-demand inference is billed per input and output token. Temperature doesn't change the price, and training data size and training time affect customization costs, not inference costs.

</details>

### Q56
*Domain 5: Security, Compliance, and Governance · Multiple Choice*

An AI company periodically evaluates its systems and processes with the help of independent software vendors (ISVs). The company needs to receive email message notifications when an ISV's compliance reports become available. Which AWS service can the company use to meet this requirement?

- A. AWS Audit Manager.
- B. AWS Artifact.
- C. AWS Trusted Advisor.
- D. AWS Data Exchange.

<details><summary>Show answer</summary>

**Answer: B**

AWS Artifact gives on-demand access to compliance reports, including third-party (ISV) reports through Artifact third-party reports, and can send notifications when new reports become available. Audit Manager collects your own evidence, and Data Exchange is for data products.

</details>

### Q57
*Domain 3: Applications of Foundation Models · Multiple Choice*

A company wants to use a large language model (LLM) on Amazon Bedrock for sentiment analysis. The company needs the LLM to produce more consistent responses to the same input prompt. Which adjustment to an inference parameter should the company make to meet these requirements?

- A. Decrease the temperature value.
- B. Increase the temperature value.
- C. Decrease the length of output tokens.
- D. Increase the maximum generation length.

<details><summary>Show answer</summary>

**Answer: A**

Lower temperature makes token selection more deterministic, so the same prompt produces more consistent output, which is ideal for classification tasks such as sentiment. Higher temperature adds variety, and output length settings don't affect consistency.

</details>
---

## Answer Key

| Q | Ans | Domain | Q | Ans | Domain | Q | Ans | Domain |
|---|---|---|---|---|---|---|---|---|
| Q1 | A | D5 | Q2 | C | D3 | Q3 | C | D2 |
| Q4 | C | D4 | Q5 | A | D1 | Q6 | B | D1 |
| Q7 | B | D4 | Q8 | B | D2 | Q9 | B | D2 |
| Q10 | A, C | D4 | Q11 | B | D4 | Q12 | A | D1 |
| Q13 | B | D5 | Q14 | A | D1 | Q15 | D | D3 |
| Q16 | A | D2 | Q17 | A | D2 | Q18 | A | D2 |
| Q19 | A | D2 | Q20 | D | D1 | Q21 | A | D2 |
| Q22 | B | D5 | Q23 | D | D4 | Q24 | A | D5 |
| Q25 | B | D1 | Q26 | C | D5 | Q27 | B | D1 |
| Q28 | C | D1 | Q29 | A | D3 | Q30 | C | D1 |
| Q31 | C | D2 | Q32 | A | D4 | Q33 | B | D1 |
| Q34 | A | D3 | Q35 | C | D1 | Q36 | A | D5 |
| Q37 | A | D3 | Q38 | A | D1 | Q39 | C | D1 |
| Q40 | C | D1 | Q41 | B | D1 | Q42 | A | D3 |
| Q43 | A | D3 | Q44 | A | D1 | Q45 | A | D5 |
| Q46 | A | D2 | Q47 | A | D4 | Q48 | C | D3 |
| Q49 | B, C | D5 | Q50 | B | D3 | Q51 | B | D3 |
| Q52 | D | D4 | Q53 | B, D | D1 | Q54 | A | D3 |
| Q55 | A | D2 | Q56 | B | D5 | Q57 | A | D3 |

## Score Tracker

| Domain | Questions | Your Score |
|---|---|---|
| 1. Fundamentals of AI and ML | 17 | ___ / 17 |
| 2. Fundamentals of Generative AI | 11 | ___ / 11 |
| 3. Applications of Foundation Models | 12 | ___ / 12 |
| 4. Guidelines for Responsible AI | 8 | ___ / 8 |
| 5. Security, Compliance, and Governance | 9 | ___ / 9 |
| **Total** | **57** | **___ / 57** |

> Aim for **46+ (81%)** before booking the exam. Review the explanations for every question you missed, then revisit that domain in `extra-details-notes.md`.
