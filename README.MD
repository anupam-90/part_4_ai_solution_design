# Task 8: Final solution summary 
DATASET link: https://drive.google.com/drive/folders/1QnXVOGNOP6o9tx_nJpTsVqd0irSLx789?usp=drive_link
## 1. Business problem: 
High-volume manufacturing lines currently face significant bottlenecks and quality escapes due to the limitations of manual visual inspection. Relying on human QA inspectors leads to fatigue-driven inconsistencies, with recent data showing error rates fluctuating up to 11.16% and manual processing consuming over 500 hours per month. This limits total factory throughput and allows defective products to reach end-users, negatively impacting customer satisfaction.

## 2. Proposed AI Solution: 
Implementation of an AVI(Automated Visual Inspection) powered by computer vision. High speed, IoT-enabled industrial cameras will be mounted over the conveyor belts to capture images of every product. An AI model will analyze these images in real-time, classifying them as either Non-defective(Pass) or Defective(Fail) using CNN with Transfer Model Learning.

## 3. Required Data 
Data type: Unstructured, high resolution image data(RGB)
Input features: Pixel intensity and spatial patterns capturing the surface texture of the manufactured parts. 
Target Variable: Binary label(Categorical labels 0 for good and 1 for defective)
Collection: Thousands of historical and actively collected images from the factory floor under controlled lighting, accurately labeled by senior QA engineers. 
## 4. Model Reccomendation
Convolution Neural Network(CNN) utlizing Transfer Learning(eg., ResNet50)
## 5. Expected business impact
Quality Improvement: Reduction of the current average eerror rate to under 2% which is currently 7%(approx)
Cost & Time efficiency: a 50% to 60% reduction in manual processing hours, freeing up the workforce for higher level tasks
Increased Throughput: With faster average resolution times, it will allow for a higher volume of 'monthly_cases' processed. 
Customer Satisfaction: With fewer defective products making it out ot the production, customer Satisfaction Score will increase from the current average of 6.9. 
## 6. Risks and mitigation plan

    -Risk 1: Environmental Bias(lighting changes)
    The model may fail during night shifts if ambient factory lighting changes. This can be mitigated using LED lighting arrays at the camera stations. With use of "Data Augmentation" to make the model robust to lighting shifts. 

    -Risk 2: Over-reliance and Edge Cases
    The system might confidently misclassify a rare, previously unseen defect type. To mitigate this implementing HITL(Human-in-the-loop) protocol, any prediction with a confidence score between 40% and 75% will automatically flag the image for namual review by a human QA specialist. 
