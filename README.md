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






