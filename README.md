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
#### Case study: speech reg
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
#### Challenges: statistical issue & software engine issue
- Data drift (X) : Lighting condition changes -> distribution of data changes
- Concept drift (X->Y) : inflation -> price changes when size of house remains
- Software engine issue:
  + Realtime or batch
  + Cloud (has more computing resource) or Edge (visual inspection in factory)
  + Computer resources (CPU/GPU/memory) - not enough powerful GPU for deployment
  + latency (QPS)
  + logging
  + secutiry & privacy (patient record highly sensitive) 
  





