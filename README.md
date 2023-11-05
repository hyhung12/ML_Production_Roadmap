![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/8b4db2b6-a722-4898-91cb-fa8ca06d9b70)
<p float="left">
  <img src="https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/7f6eb620-f4dc-42a3-bb7b-78e13d3dd8c6" width="48%" />
  <img src="https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/f90f0d01-7e37-4e9a-b598-146e5e7646d4" width="48%" />
  <img src="https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/f90f0d01-7e37-4e9a-b598-146e5e7646d4" width="48%" />
  <img src="https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/f90f0d01-7e37-4e9a-b598-146e5e7646d4" width="48%" />
</p>

![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/7f6eb620-f4dc-42a3-bb7b-78e13d3dd8c6)
![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/f90f0d01-7e37-4e9a-b598-146e5e7646d4)
- Deloying a system is just halfway
- Lighting conditions in factory can be changed compared to the time training set was collected
-> Concept drift or data drift
![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/89081cde-b197-405b-95b4-91506b22235a)
![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/3e331342-8e0e-4df1-a279-59c3b0c45f29)
-> Systematically plan out the full lifecycle of a ML project
![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/2b037768-91fb-433d-ba95-d417e01626fd)
- MLOps (ML Operations) : emerging discipline (consists of tools & principles to support progress) <- used to be done manually <- LandingLens
- **key: systematically ways to think about scoping, data, modeling and deployment, software tools**
- Speech recoginition: one of the successes of Deep Learning (valuable production deployment system)
## Case study: speech reg
+ **Scoping: Define project**
  - Key metrics: accuracy, latency
  - Estimate resources & timeline
+ **Data:**
  - Is data labeled consistently
  - Train or test set can be edited to improve the production system
+ **Model: train & perform data analysis**
  - In production, data > model
  - Error analysis -> improve the data systematically, no need to collect more data
+ **Deployment:**
  - Design system for adult but then most teenagers use
## Challenges: statistical issue & software engine issue
- Data drift (X) : Lighting condition changes -> distribution of data changes
- Concept drift (X->Y) : inflation -> price changes when size of house remains
- Software engine issue:
  + Realtime or batch
  + Cloud (has more computing resource) or Edge (visual inspection in factory)
  + Computer resources (CPU/GPU/memory) - not enough powerful GPU for deployment
  + latency (QPS)
  + logging
  + secutiry & privacy (patient record highly sensitive)
## Common deployment cases:
**1. New product**<br>
**2. Automate/assist with manual task**<br>
**3. Replace previous ML system**
## Deployment modes:
- **shadow mode:** ML system shadows human and runs in parallel
- **canary mode:**
  + (used in coal mine to spot gas leak) roll out to small fraction (5%) of traffic initially
  + monitor system and ramp up traffic gradually -> spot problems early on
- **blue green mode:** keep old and new model -> easy way to enable rollback
- **Degree of automation:**
Human only -> Shadow mode -> AI assistance -> partial automation (maybe good) -> full automation
# Modeling
## Challenges when monitoring deployed ML system:
- Use dashboard to track how system doing overtime
- Set threshold for alarm
- Okay to start with many metrics then gradually removes a few that not useful (combine input & output metrics)
- Deployment also highly iterative process - does take a few tries -> Also need maintenance
- Pipeline: may involve 2 or more learning algorithm
  + user data has slower drift
  + enterprise data(B2B app) can shift fast
- Low avg error not always good -> skewed data distribution
## Establish baseline (should do for long-term success)
- May hire human to set HLP (Human Level Performance)
- HLP less useful baseline for structured data
- **Tips:**
  + Find reasonable sources to get started, no need to search for latest algorithm
  + **Reasonable algorithm with good data will oftern outperform a great algorithm with no so good data**
## Error Analysis
- Can be done manually
![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/3ad8a493-e60b-408c-8dc8-aea8fcf347cc)
## Prioritize what to work on
- Work on 1% but huge % data -> more improvement on overall accuracy
![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/194d01eb-5d3a-4d9b-8c2f-fcad0021ce68)
- Choose categories to work on:
  + How much room for improving
  + How frequent that category appears
  + How easy to improve accuracy
  + How important to improve
- Collect more data is good but time-consuming & expensive -> carry out analysis -> focus exact kind of data
## Skewed dataset
- Raw accuracy is not a good metrics (precision & recall)
- Precision = TP / (TP + FP), Recall = TP / (TP + FN)
- High recall > preicison
## Performance Auditing
## Why data-centric AI development?
- Most academic research - download a benchmark dataset and try to do well on that benchmark <- model-centric
## Data augmentation
- Create realistic examples that the algorithm  does poorly but humans (baseline) do well -> good way to improve performance
- Create realistic images or use photoshop to draw a stratch
## Adding more data
- For unstructured data, adding data rarely hurts accuracy
- For structured data, hard to create more data -> add more features (maybe better than add more users)
- Also, no baseline to compare
- For unstructured data, deep learning is very good at identifying features
## Experiment tracking
- Should have a system to track past experiments
![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/27424fa2-5fc8-45df-a16c-ea6da49719e2)
- Good data -> key to high performance and reliable ML deployment:
  + Cover important cases
  + Good distrbution (cover data and concept drift)
## Data definition (labeling)
- Inconsistent label (different bounding box style) or label ambiguity
- Again, human are good at unstructured data
- Small data (<10000) and big data (>10000)
- Should have small teams to have same data definition
## If small dataset then it should be clean and consistent
- **Label consistency**<br>
![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/d810ebc8-6736-4b58-b12c-2f819fdee200)
- Merge classes -> get rid of inconsistencies
- Can create ambiguous classes : clear, not clear and no clear
- Use voting for many labelers
- Lack of tools -> carry out process consistently & repeatedly
## Label and organize data
- Dont spend so many days just to collect data
- Labeling data options: **In-house** & **Outsourced** & **Crowdsourced**
- MLEs to label data -> expensive but can build intuition
- May need experts to help labeling
- No need to rapidly increase the data
- **Should start with small dataset -> error analysis -> get intuition -> increase dataset**
![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/42a2614d-686d-4c6b-9fe7-1fb843f68c6d)
## Metadata (data of data/ side data)
## Planing AI project (think carefully to create value)
- 1/ Think about business prolbme
- 2/ Think about AI solutions (not all problems can be solved with AI)<br>
![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/4490936c-02b5-4f96-bf78-c16f2e9fb04d)
- If a task is done well by human -> can plan an AI solution
- If features are not predictive -> hard to create AI solution
![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/cf96ceee-7827-43f5-8ae5-0d952e318785)




## Data - MLE in Production
- Real-world data is dynamic and usually shifting
- In ML: data is first-class citizen (data should have predictive content)
- ![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/a11f9832-9104-4613-96da-193d776ddab4)

![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/9f79c83f-695c-4f83-b2d6-818abf9c1b14)
- The world changes so does the data
- Camera are moved
## Model Serving
- Challenge: tradeoff between model's predictability & speed of latency
- ![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/d0ed3e26-e044-4599-b665-6fb1c9d270ea)
- Caching: GGC Memorystore, AWS DynamoDB
- 2 environments to deploy: edge devices (memory constraint) & cloud (REST API) but not good for app that prediction latency is important
- gRPC maybe better than REST
- ![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/59be1dba-e36a-4e2b-9502-b68833c0d0d0)
- Scaling Infrastructure: Vertical (Have a bigger car), Horizontal (Lease more cars to less rely)
- Container - convenient way to do horizontal scaling
- ![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/75366b49-8125-4a60-9982-1cd4390fa104)
- Data in model -> pre-processing, data out -> post-processing
- Batch data (csv file, log file) & Streaming data (data from sensors)
- ![image](https://github.com/hyhung12/ML_Production_Roadmap/assets/97202476/fee30aa9-a21f-440c-89e4-2ae93e7394bf)
- ML - experimental science (experimenting & analyzing - heart of ML development)
- Notebooks are powerful tool but not good for production environment
- Modular code, not monolithic -> production level experiment
- Need tool for Data Versioning
## Model Decay
- Detected by observe statistical properties of logged data or using dashboard
- If it happens, can start over or fine tune




