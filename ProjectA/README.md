
Here is the explanation of what is included in the Supplementary file:
    
    1.Task1.ipynb is a Python notebook showing how the teacher and student models are trained in the conventional KD framework. You will use this file to implement conventional KD for the MNIST dataset.

    2. Project_A_FAQs.pdf is a list of Frequently Asked Questions that try to throw light on (almost) all of your questions and concerns that you may have during Project A.

    3. Task2.ipynb is a Python notebook showing how the teacher (Pre-tained ResNet50V2) and student models (pre-trained MobileNetV2) are trained in the conventional KD frameworks. 

    4. Report.pdf is a report for the project A and include the explanation and result for both task 2.ipynb and task1.ipyb. 

    5. annotations.csv. Note that this file includes each image file name and its corresponding majority-vote label and degree of annotator agreement expressed as the number of annotators who marked the image as SSA (e.g., 6 indicates 6/7 agreement with a ground truth of SSA, and 2 would indicate 5/7 agreement with a ground truth of HP).

Task 1. ipynb Introduction:
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
    
    10. Implementing the state-of-the-art KD algorithm (part a):

    11. Implementing the state-of-the-art KD algorithm (part b):

    12. XAI Implement:


Task 2. ipynb Introduction:

    

