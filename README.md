*NOTE:* This file is a template that you can use to create the README for your project. The *TODO* comments below will highlight the information you should be sure to include.


# Operationalizing The Machine Learning Model In Azure

The main objective of this project is to build a machine learning model using Azure Container Services.We have been provided with the banking dataset.
The main steps of the project are

    1) Authentication
    2) Automated ML Experiment
    3) Deploy the best model
    4) Enable logging
    5) Swagger Documentation
    6) Consume model endpoints
    7) Create and publish a pipeline
    9) Documentation

## Architectural Diagram
*TODO*: Provide an architectual diagram of the project and give an introduction of each step.
![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/flowchart.png "Logo Title Text 1")

## Key Steps
   # Register the Dataset
   - We have to first register the dataset from the local files.
        - Navigate to the Datasets section in the Workspace and create a new dataset from webfile and submit the URL required for the dataset
   ![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Dataset.png "Logo Title Text 1")<br>
   
   
   # Compute Instance 
   - We have to build a compute instance of type DS12_V2 for running the AutoML Run. 
     - Maximum number of nodes are 5 and min number of nodes are 5.
        
        
   # AutoML Run<br>
    
   - We have to run an AutoML using the same regitered Dataset.
   - We have to mention the same compute instance which we build earlier.
   ![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/AutoML%20RUN.png "Logo Title Text 1")
    
    
   # Best Model
   - After running the AutoML we need to collect the best model from various diffrent models.<br>
        - Here we got voting ensemble model which chooses voting model to choose the best of several runs. The base model is XGBOOST with Maxabs scaling and accuracy of 91%                               .
        
   ![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Best%20Model.png "Logo Title Text 1")
   
   # Endpoint Deployment
   
   - Once we Have the best model its time to deploy the model. We can use azure Kubernetes service or azure container instane for the deployment.
   - We need to choose authenticate method during the deployment method. Once deployment is succeded an endpoint will be created with status showing as healthy in workspace
    
   # Application Insights
   
  - Once the model is deployed we need to enable the logs setting the appinsights = True in the Experiment logging section by adding the experiment name.
  - Once we have enabled the logging we should see the status in application insights saying the failed requests, timed out requests etc.
   
   
    
   ![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Deploy.png "Logo Title Text 1")
   
  # Consume Endpoint (Swagger)
   - We can consume this endpoint using REST API or by running Azure ML python SDK's. 
   - Swagger is one of the API tetsing platforms available . 
   - Once the model is deployed we get a Swagger JSon file from the endpoint which needs to be downloaded and placed in the folder containing swagger files serve.py and swagger.sh.
  - After that we need to launch a local web server using serve script and lauch swagger using docker container by running swagger.sh
  
  - Here we are testing both using endpoint.py and Swagger
 ![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Swagger.png "Logo Title Text 1")
  
  
  # Creating and Publishing pipeline 
  We can schedule the pipelines using schdeule recurrence parameter reducing the manual efforts.
  
  ![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Pipeline%20in%20azure.png "Logo Title Text 1")
  
![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Pipeline%20details.png "Logo Title Text 1")
  
![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Run%20Complete.png "Logo Title Text 1")
  
 ## How to Contribute ? ✨
 Check out our [contributing guidlines](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/CONTRIBUTING.md)
        


## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:
# https://youtu.be/GXZqAYFzaJ8

## Standout Suggestions
* Collecting more data can definietly help in improving accuracy.
* We can try tesing the batch data in a shcedule and see the performance.

## ❤️ Thanks to our awesome contributors ✨✨.
<table>
  <tr>
    <td>
        <a href="https://github.com/vaibhavirohilla741/Operationalizing-ML/graphs/contributors">
            <img src="https://contrib.rocks/image?repo=vaibhavirohilla741/Operationalizing-ML" />
        </a>
    </td>
   </tr>
</table>
