![](assets/banner.gif)
# Operationalizing a Machine Learning Model In Azure:rocket:

The main objective of this project is to <strong>build a machine learning model using Azure Container Services</strong>.We have been provided with the banking dataset.
The main steps of the project are:-

    1) Authentication
    2) Automated ML Experiment
    3) Deploy the best model
    4) Enable logging
    5) Swagger Documentation
    6) Consume model endpoints
    7) Create and publish a pipeline
    9) Documentation

## Tech-Stacks:
<img alt="Jupyter" src="https://img.shields.io/badge/Jupyter%20-%23F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white" /> <img alt="Python" src="https://img.shields.io/badge/python%20-%2314354C.svg?&style=for-the-badge&logo=python&logoColor=white"/> <img alt="Shell Script" src="https://img.shields.io/badge/shell%20-%23121011.svg?&style=for-the-badge&logo=gnu-bash&logoColor=white"/>  <img alt="Azure" src="https://img.shields.io/badge/azure%20-%230072C6.svg?&style=for-the-badge&logo=azure-devops&logoColor=white"/>  <img alt="Docker" src="https://img.shields.io/badge/docker%20-%230db7ed.svg?&style=for-the-badge&logo=docker&logoColor=white"/> <img alt="Swagger" src="https://img.shields.io/badge/Swaggeer%20-%23107C10.svg?&style=for-the-badge&logo=Swagger&logoColor=white"/>

## Architectural Diagram:clipboard:
An architectual diagram of the project and introduction of each step.
![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/flowchart.png "Logo Title Text 1")


## Authentication
It is the vital step to ensure secure and authentic access. Authentication is required for the creation of the Service Principal account and associate it with specific workspace.

## Automated ML Experiment
We create the new Automated ML Run Experiment and then upload the Bank Marketing dataset. We run the experiment configuring a new compute cluster, using Classification and ensure that the best model explaination is enabled.

## Deploy the Best Model
After the completion of the AutoML Run, we will get our best model. We will then deploy that model using the **Azure Container Instance(ACI)** and enable **Authentication** to prevent unauthorized access.

## Enable Logging
After the deployment, we will enable the Application Insights from the deployed model. This will help us produce logging output with the python sdk. It plays a vital role to debug problems in production environments.

## Swagger Documentation
Swagger helps us build, document and consume RESTful web services. It also explains what type of requests API can consume like **POST** and **GET**.

## Consume Model Endpoints
We must consume the deployed service to retrieve the data using **HTTP request**. It will help us in validation of data by identifying if anything is having any problem or is incorrect.

## Create and Publish Pipelines
The last and the most vital step is to make the model publically available. This is done by creating a pipeline and then publishing it. It is synonymous to Automation as the pipeline create ways for other services to interact with it using HTTP endpoint.

## Key Steps:tickets:
   # :pushpin:Register the Dataset
   - We have to first register the dataset from the local files.
        - Navigate to the Datasets section in the Workspace and create a new dataset from webfile and submit the URL required for the dataset
   ![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Dataset.png "Logo Title Text 1")<br>
   
   
   # :pushpin:Compute Instance 
   - We have to build a compute instance of type DS12_V2 for running the AutoML Run. 
     - Maximum number of nodes are 5 and min number of nodes are 5.
        
        
   # :pushpin:AutoML Run<br>
    
   - We have to run an AutoML using the same registered Dataset.
   - We have to mention the same compute instance which we build earlier.
   ![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/AutoML%20RUN.png "Logo Title Text 1")
    
    
   # :pushpin:Best Model
   - After running the AutoML we need to collect the best model from various diffrent models.<br>
        - Here we got voting ensemble model which chooses voting model to choose the best of several runs. The base model is XGBOOST with Maxabs scaling and accuracy of 91%
        - After the experiment run completes, a summary of all the models and their metrics are shown, including explanations. Below images show the explaination of the best performing model.
        
   ![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Best%20Model.png "Logo Title Text 1")
   ![gssoc1](https://user-images.githubusercontent.com/61888364/112888309-d03b5700-90f1-11eb-8d1a-63aa928f878b.png)
![gssoc2](https://user-images.githubusercontent.com/61888364/112888314-d2051a80-90f1-11eb-8a50-ad9ea5eb67b6.png)
   
   # :pushpin:Endpoint Deployment
   
   - Once we Have the best model its time to deploy the model. We can use azure Kubernetes service or azure container instane for the deployment.
   - We need to choose authenticate method during the deployment method. Once deployment is succeded an endpoint will be created with status showing as healthy in workspace
    
   # :pushpin:Application Insights
   
  - Once the model is deployed we need to enable the logs setting the appinsights = True in the Experiment logging section by adding the experiment name.
  - To enable Application Insights, we run the logs.py file.
    ![gssoc3](https://user-images.githubusercontent.com/61888364/113008907-18f81c00-9195-11eb-8854-60466b896638.png)
    ![gssoc4](https://user-images.githubusercontent.com/61888364/113008914-1b5a7600-9195-11eb-93e3-a82ea3006f83.png)


  - Once we have enabled the logging we should see the status in application insights saying the failed requests, timed out requests etc.
   
   ![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Deploy.png "Logo Title Text 1")
   
  # :pushpin:Consume Endpoint (Swagger)
   - We can consume this endpoint using REST API or by running Azure ML python SDK's. 
   - Swagger is one of the API tetsing platforms available . 
   - Once the model is deployed we get a Swagger JSon file from the endpoint which needs to be downloaded and placed in the folder containing swagger files serve.py and swagger.sh.
  - After that we need to launch a local web server using serve script and lauch swagger using docker container by running swagger.sh
  
  - Here we are testing both using endpoint.py and Swagger
 ![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Swagger.png "Logo Title Text 1")
  
  
  # :pushpin:Creating and Publishing pipeline 
  We can schedule the pipelines using schdeule recurrence parameter reducing the manual efforts.
  
  ![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Pipeline%20in%20azure.png "Logo Title Text 1")
  
![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Pipeline%20details.png "Logo Title Text 1")
  
![alt text](https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/Screenshots/Run%20Complete.png "Logo Title Text 1")
  
## How to Contribute ?:heavy_plus_sign::spiral_notepad:
Check out our <a href="https://github.com/vaibhavirohilla741/Operationalizing-ML/blob/main/CONTRIBUTING.md">CONTRIBUTING GUIDELINES</a>
        
## See project in action <a href="https://youtu.be/GXZqAYFzaJ8">HERE<a>:framed_picture:

## :eight_spoked_asterisk:Standout Suggestions:eight_spoked_asterisk:
* Collecting more data can definitely help in improving accuracy.
* We can try testing the batch data in a schedule and see the performance.
* We can try to implement various new algorithms along with running the AutoML Experiment for a longer time period.
* We can try new values for number of nodes, concurrency etc.
* We can use GPU's instead of CPU's to improve the performance. Since CPU's might reduce the costs but in terms of performance and accuracy GPU's outperform CPU's.

## ❤️ Thanks to our awesome contributors:technologist:✨.
<table>
  <tr>
    <td>
        <a href="https://github.com/vaibhavirohilla741/Operationalizing-ML/graphs/contributors">
            <img src="https://contrib.rocks/image?repo=vaibhavirohilla741/Operationalizing-ML" />
        </a>
    </td>
   </tr>
</table>

## LICENSE
This project is licensed under the [MIT LICENSE](LICENSE)
