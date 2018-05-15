# Introduction 
> This is BAIOPS Revenue Prediction Project

# Getting Started
1. Install docker package
    > For Ubuntu

        apt-get install docker
    > For CentOS / RHEL

        yum install docker
    > For MacOS

    dwnload the dmg file from below link:
    ​    
        https://download.docker.com/mac/stable/Docker.dmg
    OR
    ​    
        brew cask install docker
2. Pull image

        docker pull BAIOPS/RevenuePrediction:v1.0
3. Download the run.sh
   ​      
        You need a network path to place the script, you can put it on BAIOPS's Azure, and then you give it a path
        wget http://baiops.com/files/run.sh
4. Add executable permission to run.sh

        chmod +x run.sh
5. Now run the run.sh, add your data file path, and you can see the prediction result!

        ./run.sh -input your_data_file.csv [-config config.ini]   

6. The example result:

   ```
    Assign the example output here
   ```
# Revenue Prediction Introduction

>This model mainly predicts the user consumption. It only needs to input the training data set and specify the characteristics and prediction targets to complete the training of the prediction model. At the same time, the model can be evaluated by using the test set. As the following figure shows, the training features have basic information: age, gender, region, industry;
Consumption capacity: consumption cycle, consumption amount, consumption level;
Browsing record: browsing time, browsing goods;
Forecast target is consumption amount (characteristics and targets are not limited to these, different industries can customize themselves)

![](https://github.com/BCI-Athena/RevenuePrediction/blob/master/Images/RevenuePrediction-EN.png)

##### Training Data Set
+ Data set format:.csv
+ Features: Supports Number, String, recommended as Number
+ Predict target:Number
+ Tips:Data sets are preprocessed and null not allowed to exist

##### Testing Data Set
+ Data set format:.csv
+ Features: Supports Number, String, recommended as Number
+ Predict target:Number
+ Tips:Data sets are preprocessed and null not allowed to exist;and include predict target for evaluating models

##### Config description
>Config.ini. can be downloaded officially, and the user changes the file to configure the dataset, features, prediction targets, and mirroring versions, as shown in the following table:

| **Key**             | **Description**      | **Examples**                               |
| :------------------ | :---------- | :----------------------------------- |
| data_dir            | Data set directory     | /home/hb/docker_file                 |
| train_data          | Training data set name     | train_1w.csv                         |
| test_data           | Testing data set name     | test_2k.csv                          |
| test_data_predicted | Testing data set predict result name | predicted.csv                        |
| eval_data           | Evaluation result file name    | eval.csv                             |
| features            | Features          | ['feature1', 'feature2', 'feature3'] |
| predict_target      | Predict Target        | ['target1,' target2']                |
| imageVersion        | Mirror version        | models:v7                            |

##### Training and Predict
>You can download run.sh and config.ini, modify the configuration file to execute the following command training model and get the predicted results, as shown in the following figure

```
./run.sh config location direatory/config.ini
```
![](https://github.com/BCI-Athena/RevenuePrediction/blob/master/Images/RevenuePrediction-directive.png)
