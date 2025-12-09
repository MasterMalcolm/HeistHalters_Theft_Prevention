# HeistHalters Theft Prevention by ScreenScavers
THEFT PREVENTION using a Computer Vision Solution 

Team: Khalida Bestani, Malcolm Richardson, R. Brandon Thompson

This repository contains a project proposal to a real world solution. 

Tier 3 - We want the system to analyze the motion to determine if a theft is in progress. If a theft is determined, the authorities will be alerted by the system.

Problem Statement: 
  Museums lost over $5 billion last year to thefts and damages. Traditional security systems are too expensive and cannot monitor every exhibit at all times and respond fast enough to prevent loss or damage. There     is an urgent need for affordable real-time security that prevents loss and damage before it happens for institutions of all sizes.

Solution Overview: 
  THEFT PREVENTION using a Computer Vision Solution that spots when someone is getting too close to the exhibits or is acting suspicious. The model identifies threatening or sketchy behavior, filters out false     alarms while verifying actual threats to then alert security in real time.

  Object Detection (OD) and Action Recognition (AR) to detect people and identify their behavior. Just watching people is not enough. OD to detect people and products. AR to identify suspicious behavior, "theft"       and track the suspects throughout the building(s). Neuroevolution to evolve from new data and improve continuosly. Evolutionary Video Deep Learning learns patterns that evolves better architecture or                 strategies for learning those patterns.

  Deep spatiotemporal learning and continual learning through: Convolutional 3D Neural Networks, Recurrent Neural Networks and Video Tranformers

  UCF-Crime or Anomaly Detection datasets - has actual suspicious behavior videos COCO - has people, bags, products (good starting point) Roboflow - search for "shoplifting detection" or "retail security" datasets     Unity Perception - synthetic datasets that allow us to generate correct labels that would be difficult to get in actual museums.Can build "scenes" for bounding box and labeler to capture boundaries, person           crossing boundaries, hands, gestures, artifacts, reaching, bags, etc

Technical Approach (technique, model, framework)-Technique: Object Detection & Classification​

​  Model: YOLOv8 trained on behavioral, theft detection, and action recognition datasets from COCO, RoboFlow Universe, UCF-101​

  Framework: PyTorch handles 30+ fps real-time video analysis for threat events with no lag time between threat event and alert being sent out. Flexible to fine-tune for threat behaviors.​

​  Justification: Enables fast, real-time detection and classification, providing a reliable and practical solution for protecting valuable museum artifacts. Has access to proven real-world detection models ​

Dataset Plan (source, size, labels, link if public) - 

  Specialized behavioral datasets 📊 will be collected from COCO's Keypoint detection. 🔍Train, validation and test sets that have more than 200,000 available images.​

  Roboflow Universe's open-source shoplifting/gesture datasets 📊 will help our model learn typical movement patterns before we train it on real museum scenarios to provide a solid foundation. 🤖​


Technical Approach (technique, model, framework) Import the following libraries and framework: 

  Ultralytics for YOLOv8 that looks for and identifies people, actions, exhibits and other objects in images is ultimately the brain for our AI system; 

  Opencv-python-headless to read video files and break them into individual frames; 
  
  PyTorch framework (torch and torchvision) to build and train the neural networks performing math calculations learning from examples during training and run      predictions on new videos, inference; 
  
  Transformers to connect images to text descritpion and generate explanations, utilizing CLIP and BLIP, to reduce false alarms by understanding the intent and     not just actions; 
  
  Scikit-learn to calculate accuracy, precision, recall and F1-scores through splitting our data into training, validation and testing groups creating confusion    matrices showing which behaviors our AI confuses; 
  
  Matplotlib and Seaborn show results with visual charts and graphs helping track training curves and prove the system is working; 
  
  Pytorchvideo for analyzing frame sequences and understand behavior over time. Our system balances a lot of competing demands simultaneously including
  tediously composing datasets, continuous active learning that improves detection and minimizes human labeling, real-time image processing at 20-30 fps, and      high recall in order to be successful.  

Dataset Plan (source, size, labels, link if public) A strong foundation is built for our behavioral theft detection system using multiple sources to avoid bias by combining large-scale datasets for training and specialized behaviorial  data for rare theft events used for fine-tuning.  UCF-101 has more than 13,000 videos that cover 101 action categories that has demonstrated 96% accuracy with YOLO architectures which brings us to believe is ideal for the intial transfer learning. UCF-Crime or Anomaly Detection datasets has actual suspicious behavior videos. COCO has people, bags, products (good starting point) Roboflow for "shoplifting detection" or "retail security" datasets. Unity Perception synthetic datasets that allow us to generate correct labels that would be difficult to get in actual museums. Can build "scenes" for bounding box and labeler to capture boundaries, person crossing boundaries, hands, gestures, artifacts, reaching, bags, etc

  Unity Perception open-source package provides synthetic data for computer vision by training the synthetic datasets on a 2D object detection model.  🤖​

  UFC-Crime Dataset for anomaly detection to identify and label abnormal and normal behavior. The system learns to detect anomalies by comparing patterns and context to what is "normal."​ 10,000-20,000 high-quality     labeled data images needed to train, validate and test model​

​  https://universe.roboflow.com/search?q=class%3Ashoplifting​

  KAGGLE Datasets:
    
https://www.kaggle.com/datasets/kipshidze/shoplifting-video-dataset

https://www.kaggle.com/datasets/gti-upm/leapgestrecog

https://www.kaggle.com/datasets/mateohervas/dcsass-dataset

https://www.kaggle.com/datasets/momanyc/museum-collection

https://www.kaggle.com/datasets/ziya07/hajj-and-umrah-crowd-management-dataset

Metrics (primary + secondary)

  Primary Metric:  Our model prioritizes recall because failing to identify actual thefts costs 5-20x less than looking into false alarms. False negatives result in money lost with every undetected theft, legal       issues and possible regulatory penalties. False positives create friction among the staff, can cause alarm fatigue then real threats get ignored or missed. False alarms do not have the catastrophic outcomes such     as the loss of multi-million dollar or even priceless artifacts. This leads us to optimize for high recall first then fine tune the precision as we go.​

  Secondary Metrics: Precision target of 80-90% is achievable and realistic by training on high-quality labeled datasets of behavioral anomalies, general surveillance, and theft detection images. We also focus on       speed to maximize the efficiency from real-time detection with 50-500 4K cameras achieving 30 FPS continuous recording.​

Resources Needed (compute, cost, APIs) Changed runtime to L4 GPU to handle required video sequencing needed for this project that performs great with YOLOv8 for training. The project calls for no less than 30 frames per second (fps) and batch sizes can range between 16-32 for faster training which L4 GPU excels in and makes perfect for this project.

  Google Colab T4 GPU for primary platform to conduct initial testing. Kaggle for backup or more time if needed.​

  UCF-Crime datasets for actual footage of criminalbehaviors with a "normal" baseline to compare against. UCF requires a request form at no cost. ​

  COCO datasets to provide a baseline for detecting people near museum exhibits. Human pose gestures dataset from MPI.​

  PyTorch framework with YOLOv8 for object detection to handle desired 30 fps​

Risks & Mitigation Table

  Risk - Low accuracy, Missing data 
  Probability - Medium
  Mitigation - Use data augmentation, High Switch to Roboflow dataset

Used Claude AI for insight on what models Veesion and other top companies are using for retail prevention with AI. Claude provided a breakdown of the models used, ML domains, architectures and examples of real world use cases outside of retail theft prevention.
Copilot was used to design powerpoint slides. ChatGPT was utilized to provide information on the best datasets and how/when to implement them into training, testing or fine-tuning stages.

Leveraged Gemini to generate the foundational Python architecture for the computer vision pipeline, including the core scripts for YOLOv8 training and automated video inference. It provided a functional code base to handle complex tasks like environment setup and integrate Google Drive. This established a stable prototype, allowing us to focus on optimizing the scripts, customizing the datasets, and fine-tuning the model to meet the project's specific requirements.

Theft Demo

https://github.com/user-attachments/assets/1ffdacd1-0b5f-40ae-9a6c-00dc10f95fce
