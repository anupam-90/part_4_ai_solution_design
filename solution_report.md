## Task 1 & 2: Choosing a domain and defining the problem.

**Selected domain for the problem:** Maufacturing

**Business Problem:**
High volume production lines still rely on human inspectors to identify manufacturing flaws and physical defects like dents, scratches or missing parts. 

Stakeholders who would be involved and/or affected by the resolution of this problem is Quality Assurance teams, end customers and Production Managers.

The current process involves manual inspection under specialized lighting at the end of the assembly line which has a few *limitiations:*
    1.Human fatigue leads to increased error rates through false negatives over time.
    2. This process is a bottleneck that limits factory output to the limits of human body as well as increased cost of 'escaped' defects that reach the customer. 

## Task 3: Identify the AI Task type
AI Task Type which will be used as Image Classification since the primary goal is to categorize an image of a manufactured part into one of the 2 categories which would be Pass or Fail for non defective and defective parts respectively. This is a computer vision task where the model will learn spatial patterns like textures, edges and past defective pictures to differentiate between normal surface quality and anomalies. 

## Task 4: Data requirement plan

**Data type:** The model will require unstructured image data which should be high resolution for accurate training. 

**Input features:** RGB pixel values representing the surface of the manufactured product.

**Target variable:** Categorical label where 0 denotes "Good" and 1 denotes "Defective". 

**Data collection method:** Automatic industrial cameras mounted over the production line with synchronized trigger sensors. 

**Data quality risks:** Motion blur due to conveyor speed, lighting fluctuations and class imbalance since defects would naturally are rare occuring as compared to good parts. 

## Task 5: Model Recommendation

**Recommended Model:** Convolutional Neural Network (CNN) using Transfer Learning either ResNet 50 or EffecientNet. 

**Reasoning:** CNNs are designed to capture spatial hierarchies. By using Transfer Learning, we can take a model pre trained on millions of images and fine tune it on the factory specific defects which would significantly reduce the amount of labeled "defective" data required to achieve high accuracy. 

## Task 6: Evaluation Plan
**Technical Metrics:** The model should be critical to ensure no defective parts reach the customers, in other words minimizing False Negatives along with precision to ensure model does not discard good parts. 

**Business Metrics:** 
a. Reduction in 'error_rate_percent' where target would be less than 1%. 
b. Reduction in 'average_resolution_time_hours' per batch. 
c. Increase in 'monthly_cases' by increasing the production line speed. 

**Human Review:** A human-in-the-loop system where AI flags borderline cases(confidence score of less than 80%) for manual verification by a Quality Assurance team. 
 
## Task 7: Responsible AI considerations
*Bias in Data:* If the model is only trained from the morning shift, it can fail at night due to different lighting conditions, since it would be natural in the day and aritificial lighting in the night.

*Incorrect predictions:* During the intial phases, model would make some errors in producing the results which should be used to further train the model. 

*Privacy:* The cameras should not be capturing worker's faces around neither should the photos be stored on a database which can be accessed by anyone outside of the stakeholders mentioned above to protect the privacy of the company as well as the workers. 

*Over-reliance:* The inspectors should not stop double checking the system, especially during the initial deployment phase so that the training phase is well supervised. 

*Impact on Users:* The role of inspectors would need transform from manual sorters to AI supervisors which requires signficant upskilling and training to prepare workforce. 

