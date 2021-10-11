# Amazon SageMaker AutoPilot No-code-workshop
*No code workshop to experiment on Amazon SageMaker AutoPilot*

Introduction: Amazon SageMaker Autopilot automatically builds, trains, and tunes the best machine learning models based on your data, while allowing you to maintain full control and visibility.

 
## Download data
[This CSV file](data/churn.csv) includes customer churn data.

We use an example of churn that is familiar to all of us–leaving a mobile phone operator. Seems like I can always find fault with my provider du jour! And if my provider knows that I’m thinking of leaving, it can offer timely incentives–I can always use a phone upgrade or perhaps have a new feature activated–and I might just stick around. Incentives are often much more cost effective than losing and reacquiring a customer.



## Uploading the CSV file to S3 bucket
Amazon SageMaker imports the training data from any S3 bucket: 
<!-- let's create one to store the CSV file downloaded earlier. -->

1. Access the S3 management console by typing S3 as shown below:

![Access S3 console](pictures/console_s3.png)
 


1. Click on the name of the bucket

![Created bucket](pictures/s3_goto_bucket.png) 

3. Press **Upload**

![Upload file to bucket](pictures/s3_upload1.png)

4. Select `churn.csv` downloaded earlier by  clicking the **Add files** button.

![Upload file to bucket](pictures/s3_upload2.png)



5. Click the **Upload** button at the bottom left of the screen to start uploading.




## Go to the SageMaker screen by selecting its name from the list of services

![SageMaker Console Access](pictures/console_sagemaker.png)

1. Click on **SageMaker Studio** button on the welcome screen:

![SageMaker Landing Page](pictures/sagemaker-studio.png)

Then, press **Open Studio** on the interface below: 

![Open studio](pictures/open_studio.png)

2. From the left menu, click **SageMaker resources**, and from the SageMaker dropdown list, click   **Experiments and trials**:

![Experiments and trials](pictures/experiments.png)

3. Click on  **Create Autopilot Experiment**:

![Create Autopilot Experiment](pictures/create_experiment.png)

4. Input the required info, namely, the name of teh experiment, target column name, location of the data in Amazon S3, location of the output. 


![Autopilot](pictures/autopilot.png)

Next, Click  **Create Experiment**.

5. You will see a new window showing the steps to be completed and also a realtime view of the job status. 
   
![Autopilot status](pictures/running1.png)

6. Once Pre-processing, Candidate Definitions Generated, and Feature Engineering steps are completed and **Model Tuning** started, you can track all the training jobs and see the model names, status, and obkective values: 

![Autopilot status](pictures/running2.png)

For each trial, you can view the trial components by righ-clicking **Open in trial component list**


![Autopilot status](pictures/running3.png)


7. Compare and Analyze Trials

Select a group of trails that you plan to analyze. Make sure to select **Metrics** shown below:

![Analyze1](pictures/analyze1.png)

Sort the table entries based on **Validation:roc_auc**, and click **Add chart**

![Analyze2](pictures/analyze2.png)

On the new window, click **Add chart**

![Analyze3](pictures/analyze3.png)

You can plot a bar-chart of  **validation:roc_auc_max**

![Analyze4](pictures/analyze4.png)