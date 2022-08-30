# Airflow Apache

Apache Airflow is a powerful and widely-used open-source workflow management system (WMS) designed to programmatically author, schedule, orchestrate, and monitor data pipelines and workflows. Airflow enables you to manage your data pipelines by authoring workflows as Directed Acyclic Graphs (DAGs) of tasks.

### *prerequisite*<br/>
Docker</br>
Visual studio</br>
## Installation steps:</br>
*Create folder airflow-docker*</br>
`$ mkdir airflow-docker`</br></br>
*Get inside to airflow-docker folder*</br>
`$ cd airflow-docker`</br></br>
*Download docker-compose.yaml file*</br>
`$curl -Lf0 'https://airflow.apache.org/docs/apache-airflow/stable/docker-compose.yaml'`</br> </br>
*open visual-studio<br>
`$ code .`</br></br>
*Create dags,logs and plugins folder*
`$ mkdir ./dags./plugins/.logs`</br></br>
*Create evironment*
`$ echo -e "AIRFLOW_UID=$(id-u)\nAIRFLOW_GID=0" > .env`</br></br>
*intall airflow in docker*</br>
`$ docker-compose up airflow-init </br></br>
`$ docker-compose up  </br></br>
### Create a python file Viksara.py then create a  dag </br> ![dag1](https://user-images.githubusercontent.com/99247642/187381251-2e1ea9f1-e220-4a1c-be4d-f3423cab9570.png)</br>
* The name of the dag is Viksara</br>
* Start date: The start date is the date at which your DAG starts being scheduled. This date can be in the past or in the future. Think of the start date as the start of the data interval you want to process. For example,i have scheduled the dag to run  from 26-August-2022</br>
* schedule_interval : A schedule_interval defines a series of intervals which the scheduler turn into individual Dag Runs and execute</br>here i have scheduled dag to run after every 50 minutes</br>
 ![dag3](https://user-images.githubusercontent.com/99247642/187391639-be26277f-efad-469d-ad84-2569601786d8.png)</br>
* Retries:Number of retries that should be performed before failing the task</br>
* Retry_delay:Time taken to run tha dag again</br>
* Catch-up:An Airflow DAG with a start_date, possibly an end_date, and a schedule_interval defines a series of intervals which the scheduler turns into individual DAG Runs and executes. The scheduler, by default, will kick off a DAG Run for any data interval that has not been run since the last data interval (or has been cleared). This concept is called Catchup.</br>
### Dependencies
The training_model_A depends on training_model_B, training_model_C depends on training_models. if training_model_A fails then training_model_B will not be executed gives upstream_failed. </br></br>
![dag4](https://user-images.githubusercontent.com/99247642/187393918-2221e634-cf19-4e13-8a09-a58802819641.png)</br></br>
### Airflow dashboard</br>
* Viksara dag has been created</br>
![dag6](https://user-images.githubusercontent.com/99247642/187394681-94e2ebd7-d493-4780-964d-f2ea35a820a7.png)</br></br>
The dag run sucessfully for 61 times</br>
* Graph. training_modl_A depends upon training_model_B, training_model_B depends upon training_model_C</br>
![dag8](https://user-images.githubusercontent.com/99247642/187395851-a9cb3923-1071-488f-bc70-fd753e244cfa.png)</br></br>
* Green square indicates success status, red box shows failed status, orange shows upstream_failed status due to dependencies</br></br>
![dag56](https://user-images.githubusercontent.com/99247642/187405699-222f2be0-fda0-4bd0-9ddb-a62648ca132e.png)<br></br>

* The error, output,information are available on log tab</br>
![dag13](https://user-images.githubusercontent.com/99247642/187398094-78e684c0-8b0c-408b-b8ef-bd0272d9e6fe.png)</br></br>

![dag12](https://user-images.githubusercontent.com/99247642/187396847-51d0f4c4-ddb4-4583-826f-a26b64201218.png)</br></br>
* The return values of the function are avaiable in xcom</br>
![dag14](https://user-images.githubusercontent.com/99247642/187398336-bf6d195b-c165-44df-8677-e9a8d03d59fc.png)</br></br>
![dag15](https://user-images.githubusercontent.com/99247642/187404934-126fc485-d799-457e-8b7f-dd5bf5b42555.png)</br></br>

* We can see code of the dag on code tag</br>
![dag18](https://user-images.githubusercontent.com/99247642/187398985-4b6e0e83-f8a1-4dd6-8ccd-4a0927904b2c.png)</br></br
#### Reference video link :
https://drive.google.com/file/d/1wV1Yd47k5H9VShDTAxXxauBM9Hhhpqr0/view?usp=sharing















  








