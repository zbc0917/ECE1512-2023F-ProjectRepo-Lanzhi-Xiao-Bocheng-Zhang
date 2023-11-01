# README

### File Supplementary
Here is the explanation of what is included in the Supplementary file:
    
    1.Task1.ipynb is a Python notebook showing how the teacher and student models are trained in the conventional KD framework. You will use this file to implement conventional KD for the MNIST dataset.

    2. Project_A_FAQs.pdf is a list of Frequently Asked Questions that try to throw light on (almost) all of your questions and concerns that you may have during Project A.

    3. Task2.ipynb is a Python notebook showing how the teacher (Pre-tained ResNet50V2) and student models (pre-trained MobileNetV2) are trained in the conventional KD frameworks. 

    4. ECE1512 Report.pdf is a report for the project A and include the explanation and result for both task 2.ipynb and task1.ipyb.

    6. README.ME: Intorduce the file.

    5. annotations.csv. Note that this file includes each image file name and its corresponding majority-vote label and degree of annotator agreement expressed as the number of annotators who marked the image as SSA (e.g., 6 indicates 6/7 agreement with a ground truth of SSA, and 2 would indicate 5/7 agreement with a ground truth of HP).

### Task 1. ipynb Introduction:
The code begins by setting up the environment in Google Colab. The necessary libraries and packages, including Google Drive for data access and various machine learning and data processing packages, are imported. We separate our code for 12 parts
   
    1. Load Data: Load "MNIST" dataset and spilt to testing part and training part.
    
    2. Model Creation: CNN model as the teacher model; fc_model as the student model.

    3. Teacher Loss function: Compute subclass knowledge distillation teacher loss for given images and labels.

    4. Student Loss function: Compute subclass knowledge distillation student loss for given images and labels.

    5. Train and Evaluation: Perform training and evaluation for a given model.

    6. Train Model: Train the teacher model and student model, also train the model with different alpha and temperature.  

    7. Test accuracy vs. temperature curve: The accuracy and temperature plot shows the accuracy of the student model in different temperature with alpha = 0.5.

    8. Train student from scratch: The student model trained without Knowledge Distillation. 

    9. Comparing Teacher and Student model: Print the summary for three models (teacher model, student model and student model without KD). Also, the FLOPs for three model.
        reference code: Tokusumi, "flops_calculation.py," keras-flops, 2020. [Online]. Available: https://github.com/tokusumi/keras-flops/blob/master/keras_flops/flops_calculation.py.

    10. Implementing the state-of-the-art KD algorithm (part a): Implement SKD by the method mentioned in the  "Subclass Knowledge Distillation with Known Subclass Labels" 

    11. Implementing the state-of-the-art KD algorithm (part b): Implement TAKD by the method mentioned in the "Improved knowledge distillation via teacher assistant"

    12. XAI Implement: LIME to exmplian the model.
        reference code: Mohammadi and  S. Mahmoud, "xai_utils.py," ECE1512_2022W_ProjectRepo, GitHub, 2023.    Available:https://github.com/RezaMohammadi99/ECE1512_2022W_ProjectRepo_Seyedmahmoud-Mohammadi/blob/main/Project_A/xai_utils.py.

### Task 2. ipynb Introduction:

The code begins by setting up the environment in Google Colab. The necessary libraries and packages, including Google Drive for data access and various machine learning and data processing packages, are imported. We separate our code for 10 parts

    1. Load Model: the pre-trained ResNet50V2 model will be used as the basic teacher model. In order to customize the model we set the input shape as (224,244,3).Initially, 
        all its layers are frozen to preserve the pre-trained weights. The pre-trained MobileNetV2 model will be used as the basic student model. Meanwhile, we freeze all
        layers to preserve the pre-trained weights.

    2. Loss Function: The teacher loss computes the cross-entropy loss between the true labels and the logits. We implement knowledge distillation for the student model. The 
        combined student loss encompasses both the standard cross-entropy loss and the distillation loss. Initially, the temperature will be setted as 4 and alpha is 0.5. 

    3. Train and Evaluation: We delve into a two-phase training procedure: an initial training phase and a subsequent fine-tuning phase, each followed by an evaluation based 
        on the Area Under the Curve (AUC) metric.The initial training phase will be 12 epoch and the fine-tuning phase will be 25 epoch. In the fine-tuning phase, the learning         rate decreased devided 10. In addition, we trained models using the Adam optimizer. 
        
    4. Training Model: In this part we train the teacher model and student model. For the teacher model the learning rate will be 1e-4 and the learning rate for the student 
        model will be 1e-3.

    5. Test accuracy Vs.Temperature Curve: the temperature will be set in [1,2,4,16,32] and alpha will be 0.5. WE also test the the alpha in 0.2 and 0.5.

    6. Train Student from Scratch:The student model in this part, will be created by pre-trained  MobileNetV2 and traditional loss function. We train the model with learning 
        rate 1e-3. 

    7. Compare Teacher and Student: Print out the model summary and FLops for three model.
        Reference:Tokusumi, "flops_calculation.py," keras-flops, 2020. [Online]. Available: https://github.com/tokusumi/keras-
        flops/blob/master/keras_flops/flops_calculation.py.


    8. XAI Implement: Use LIME to do XAI explainer.
     reference code: Tokusumi, "flops_calculation.py," keras-flops, 2020. [Online]. Available: https://github.com/tokusumi/keras-
     flops/blob/master/keras_flops/flops_calculation.py.

    9.  Implementing the state-of-the-art KD algorithm (part a): Implement SKD by the method mentioned in the  "Subclass Knowledge Distillation with Known Subclass Labels" 

    10. Implementing the state-of-the-art KD algorithm (part b): Implement TAKD by the method mentioned in the "Improved knowledge distillation via teacher assistant"




    

