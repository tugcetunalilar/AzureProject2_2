![Figure 1 - Project Title ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_01_Title.png) 

# ML Engineer with Azure Nanodegree - Project 2 - ML Operations - Model Training, Deployment, Consumption & ML Pipeline Creation, Publication & Interaction  

*Overview:* This project has two main activity phases. In both the phases, the input data is the Bank Marketing dataset containing data on customer & other attributes. The goal is to make a machine learning (ML) prediction as to whether a particular bank customer will subscribe to a deposit of not. It is a 'Classification' Type Machine Learning problem. Using the features of the Azure cloud, the first phase consists of training a ML model, deploying and consuming the same. The second phase consists of creating a ML pipeine, it's configuration,publication  and creation of endpoints to interact with the same. Kindly refer to the overview diagram below.

![Figure 2 - Project Overview ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_02_Project_Overview.png)

As can be seen from the diagram above, the project was executed using the Azure Machine Learning (ML) Studio Workspace environment which is associated with an Azure ML subscription, the Azure ML Cloud infrastructure geographic region & a resource group. The project's second activity phase was run using a Jupyter Notebook.  

## Architectural Diagram

*Explanation*: Please find below an overview architectual diagram of the project. It has two activity phases.  In the 1st phase, using an automated ML run, the best model is selected, deployed and it's REST endpoints are consumed. In the 2nd phase, a ML piepline is created. This again takes the Bank Marketing data as the input and uses AutoMLStep to created a pipeline which then executes and again the best model is selected, and a published pipeline with a REST endpoint is created from where the predictions can be made. Kindly note that in the diagram below, the REST endpoints are separate in both the phases. 

![Figure 3 - Architectural Diagram ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_03_Architectural_Diagram.png)

## Key Steps
*Phase 1*: The ML Model creation & deployment has the following key steps as seen below : 

1.1 - Automated ML Experiment Creation

1.2 - Best Model Deployment

1.3 - Application Insights Enabling

1.4 - Model Endpoint Swagger Documentation Installation

1.5 - Model Endpoint Consumption

1.6 - Model Load Testing (Optional)

![Figure 4 - Phase 1 - Overview Steps ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_04_Part_1_Model_Overview_All_Steps.png) 

*Phase 2*: The ML Pipeline creation & deployment using the Jupyter Notebook has the following steps : 

- Importing Libraries

- Initializing Workspace

- Using the Azure ML experiment from the 1st phase

- Working on the Data

- Training the Data

- Examining the Results

- Creation of the pipeline's REST Endpoint

![Figure 5 - Phase 2 - Overview Steps ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_05_Part_2_Pipeline_Overview_All_Steps.png) 

## Phase 1 - Model Training, Deployment, Consumption Key Steps

1.1 - Automated ML Experiment Creation - This consists of the following tasks which result in the creation of generated ML models from which the best one is selected later for deployment.

![Figure 6 - Phase 1 - Step 1.1 ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_06_Part_1_1_Automated_ML_Experiment_Creation.png) 

Screenshot 1 below shows the availability of Bankmarketing dataset in the 'Registered Datasets' section of ML Studio.

![Screenshot 1 - Registered Dataset ](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_1_1_ML_Studio_Registered_Datasets_Showing_Bank_Marketing_Datset.png) 

In Screenshot 2 below, the completion of the AutoML Experiment is shown.

![Screenshot 2 - Automated ML Experiment Completion ](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_1_2_Automated_ML_Experiment_Shown_As_Completed.png) 

Screenshot 3 below shows the best model after completion of the experiment.

![Screenshot 3 - Automated ML Run Completion ](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_1_3_Automated_ML_Run_Completed_Best_Model.png) 

1.2 - Best Model Deployment - The best model generated in the previous task using the algorithm 'VotingEnsemble' is now selected for deployment.

![Figure 7 - Phase 1 - Step 1.2 ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_07_Part_1_2_Best_Model_Deployment.png) 

1.3 - Application Insights Enabling - For the deployed model, the 'Application Insights' are enabled programmatically. 

![Figure 8 - Phase 1 - Step 1.3 ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_08_Part_1_3_Application_Insights_Enabling.png) 

Screenshot 4 below shows the successful enabling of the deployed model 'mk-1a08-deploy's 'Application Insights' to 'True'.

![Screenshot 4 - Deployed Model Appplication Insights True ](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_3_1_Deployed_Model_Application_Insights_True.png) 

Screenshot 5 below shows the logs generated by execution of the provided 'logs.py' script against the deployed model. 

![Screenshot 5 - Deployed Model Logs ](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_3_2_Logs_By_Running_Provided_Logs_Dot_Py_Script.png) 

1.4 - Model Endpoint Swagger Documentation Installation - Azure provides a Swagger JSON file for deployed models which enable us to see the contents of their HTTP API details. The same is available after execution of the 'swagger.sh' and 'serve.py' files. 

![Figure 9 - Phase 1 - Step 1.4 ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_09_Part_1_4_Model_Endpoint_Swagger_Operations.png) 

The following 6 screenshots show Swagger running on the local host and displaying the deployed model's HTTP API methods and responses. 

![Screenshot 6 - Swagger Execution On Local Host-1 ](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_4_1_Swagger_Running_On_Local_Host_Showing_Model_HTTP_API_Methods_Responses.png) 

Swagger Screenshot 2

![Screenshot 7 - Swagger Execution On Local Host-2 ](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_4_1_Swagger_Running_On_Local_Host_Showing_Model_HTTP_API_Methods_Responses_1.png) 

Swagger Screenshot 3

![Screenshot 8 - Swagger Execution On Local Host-3 ](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_4_1_Swagger_Running_On_Local_Host_Showing_Model_HTTP_API_Methods_Responses_2.png) 

Swagger Screenshot 4
![Screenshot 9 - Swagger Execution On Local Host-4 ](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_4_1_Swagger_Running_On_Local_Host_Showing_Model_HTTP_API_Methods_Responses_3.png) 

Swagger Screenshot 5
![Screenshot 10 - Swagger Execution On Local Host-5 ](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_4_1_Swagger_Running_On_Local_Host_Showing_Model_HTTP_API_Methods_Responses_4.png) 

Swagger Screenshot 6
![Screenshot 11 - Swagger Execution On Local Host-6 ](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_4_1_Swagger_Running_On_Local_Host_Showing_Model_HTTP_API_Methods_Responses_5.png) 


1.5 - Model Endpoint Consumption - Using the provided script 'endpoint.py' after incorporating the 'scoring_uri' & 'key', a request is made to the deployed model for 2 data points and a response is received.

![Figure 10 - Phase 1 - Step 1.5 ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_10_Part_1_5_Model_Endpoint_Consumption.png) 

Screenshot 12 shows the results of the prediction response received by the script 'endpoint.py'for the two data points.

![Screenshot 12 - JSON Output From Deployed Model API](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_5_1_Endpoint_Dot_Py_Running_Against_Deployed_Model_API_Producing_JSON_Output.png)

1.6 - Model Load Testing (Optional) - In this task, the 'Apache Benchmark' tool is executed against the HTTP API to retrieve performance results. The screenshot 8 below shows the same.

<p align="center">
    <img src="http://www.kaytek.co.in/images/msudp2/diagrams/PP_10_1_Part_1_6_Model_Load_Testing.png" />
</p>

![Screenshot 13 - Apache Benchmark Run Against HTTP API](http://www.kaytek.co.in/images/msudp2/screenshots/S_1_6_1_Apache_Benchmark_Run_Against_HTTP_APPI.png) 

The above tasks are all a part of Phase 1. Now we look at Phase 2 below. 

## Phase 2 -  Key Steps

These are outlined once again and will be detailed further.

![Figure 5 - Phase 2 - Overview Steps ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_05_Part_2_Pipeline_Overview_All_Steps.png) 

- Importing Libraries which are Azure ML & Pipeline SDK specific.

![Figure 11 - Phase 2 - Step 1 ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_11_Part_2_1_Libraries_Import.png) 

- Initializing the Workspace using the 'config.json' file. Also, Azure performs an Interactive Authentication step.

![Figure 12 - Phase 2 - Step 2 ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_12_Part_2_2_Workspace_Initialize.png) 

- Using the Azure ML experiment from the 1st phase. The existing AML Compute Cluster created in the 1st phase is also reused.

![Figure 13 - Phase 2 - Step 3 ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_13_Part_2_3_Azure_ML_Experiment_Use.png) 

- Working on the Data - This entails registration of the training data as well as creation of a Pandas Dataframe for further work on the same. 

![Figure 14 - Phase 2 - Step 4 ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_14_Part_2_4_Data_Work.png) 

- Training the Data. This step involves creation of the AutoML Config parameters to be used for AutoMLStep in the subsequent pipeline creation. The PipelineRun is then started.

![Figure 15 - Phase 2 - Step 5 ](http://www.kaytek.co.in/images/msudp2/diagrams/PP_15_Part_2_5_Data_Train.png) 

Screenshot 14 belows shows the Azure ML Studio Pipeline section with the created pipeline.

![Screenshot 14 - Azure ML Studio Pipeline Section With Created Pipeline](http://www.kaytek.co.in/images/msudp2/screenshots/S_2_1_Azure_ML_Studio_Pipeline_Section_With_Created_Pipeline.png) 

In Screenshot 15 below, the active pipeline endpoint is shown.

![Screenshot 15 - Azure ML Studio Pipelines Section Showing Active Pipeline](http://www.kaytek.co.in/images/msudp2/screenshots/S_2_2_Azure_ML_Studio_Pipelines_Section_Showing_Active_Pipeline_Endpoint.png) 

- Examining the Results - This step itself has four further detailed sub steps :

- 1st, retrieval of the child run output metrics, downloading the file, deserializing the same & creation & viewing of the Dataframe for the same.

![Figure 16 - Phase 2 - Step  6-1](http://www.kaytek.co.in/images/msudp2/diagrams/PP_16_Part_2_6_1_Examine_Results_Retreive_Child_Runs_Metrics.png) 

- 2nd, best model retrieval & download for viewing it and it's steps.

![Figure 17 - Phase 2 - Step  6-2](http://www.kaytek.co.in/images/msudp2/diagrams/PP_17_Part_2_6_2_Examine_Results_Retrieve_Best_Model.png) 

- 3rd, testing the model by creating the test data Pandas dataframe and the x-test & y-test datasets.

![Figure 18 - Phase 2 - Step  6-3](http://www.kaytek.co.in/images/msudp2/diagrams/PP_18_Part_2_6_3_Examine_Results_Test_Model.png) 

- 4th & lastly, creation & inspection of the confusion matrix of the PipelineRun's best model for a better understanding of the performance. 

![Figure 19 - Phase 2 - Step  6-4](http://www.kaytek.co.in/images/msudp2/diagrams/PP_19_Part_2_6_4_Examine_Results_Confusion_Matrix_Operations.png) 

- Creation of the pipeline's REST Endpoint. In this step, the pipeline run is published, it's REST endpoint is retrieved and worked upon. 

![Figure 20 - Phase 2 - Step  7](http://www.kaytek.co.in/images/msudp2/diagrams/PP_20_Part_2_7_REST_Endpoint_Operations.png) 

Screenshot 16 shows the Bank Marketing Dataset with the completed AutoML module.

![Screenshot 16 - Bank Marketing Dataset with AutoML](http://www.kaytek.co.in/images/msudp2/screenshots/S_2_3_Bank_Marketing_Dataset_With_AutoML_Module.png) 

Screenshot 17 below gives the details of the 'Published Pipeline Overview' with the REST Endpoint as 'Active'.

![Screenshot 17 - Published Pipeline Overview Showing REST Endpoint With Active Status](http://www.kaytek.co.in/images/msudp2/screenshots/S_2_4_Published_Pipeline_Overview_Showing_REST_Endpoint_With_Active_Status.png) 

Screenshot 18 below shows the Run Execution details within the Jupyter Notebook. 

![Screenshot 18 - Jupyter Notebook Showing RunDetails Widget Step Runs ](http://www.kaytek.co.in/images/msudp2/screenshots/S_2_5_Jupyter_Notebook_Showing_RunDetails_Widget_Step_Runs.png) 

Screenshot 19 below shows the Scheduled Run within the Azure ML Studio Environment. 
![Screenshot 19 - Azure ML Studio Showing Scheduled Run ](http://www.kaytek.co.in/images/msudp2/screenshots/S_2_6_Azure_ML_Studio_Showing_Scheduled_Run_1.png) 


## Screen Recording
*Youtube Link* -  - This is a 4 minute video [screencast](https://youtu.be/jp1cDK8n8ak) showing the four essential attributes of the work done as shown below. Request you to kindly excuse the few seconds of a dark screen at the start and in between after 1:02 as I switch between the applications. Thanks for your patience and understanding.

1 - Working deployed ML model endpoint

2 - Successful API requests to the endpoint with a JSON payload.  

3 - Available AutoML Model

4 - Deployed Pipeline 

## Future Improvements 

1.0 - Input Data Enhancements - The input dataset has 20 columns / features. Prior to being fed into the ML models, they can be worked upon further to improve the model's peformance. This can be done in both the two phases. The same can also be said for AutoMLConfig settings used for the Automated ML Run in Phase 1. Since it was specifically stated that the objective of this project was to demonstrate model deployment & consumption and not improve performance, maybe the same can be done in the future. 
 
2.0 - ONNX - Future models to be generated should udeally have ONNX support for acceptability across different AI environments. This is going to be important.

3.0 - For Phase 2 - Pipeline Creation using the Jupyter notebook, I chose a compute of the following specifications : STANDARD_DS2_V2 (2 Cores, 7 GB RAM, 14 GB Disk). With a more powerful compute, the run time could have been reduced. This needs to be considered for future improvements.

4.0 - Scripts can be written for various command line console operations on the virtual machine which are repetitive. e.g. copying of certain files on the virtual machine or checking that files are in the same folder, etc. Since this part of the course focussed on automation & productivity, perhaps these utilities would be useful to save operational time.

