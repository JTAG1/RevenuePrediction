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

>This model mainly predicts the user consumption. It only needs to input the training data set and specify the characteristics and prediction targets to complete the training of the prediction model. At the same time, the model can be evaluated by using the test set. As the following figure shows, the training features have basic information: age, gender, region, industry
consumption ability: consumption cycle, consumption amount, consumption level 
browsing records: long browsing time, browsing goods 
Forecast target is consumption amount (characteristics and targets are not limited to these, different industries can customize themselves)

![](https://github.com/BCI-Athena/RevenuePrediction/blob/master/Images/RevenuePrediction.JPG)

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
>In the official download run.sh and Config.ini, modify the config to perform the following command training model and get the Predict results, the running process as shown in the following figure.

| **Key**             | **Description**      | **Examples**                               |
| :------------------ | :---------- | :----------------------------------- |
| data_dir            | 数据集存放目录     | /home/hb/docker_file                 |
| train_data          | 训练集文件名称     | train_1w.csv                         |
| test_data           | 测试集文件名称     | test_2k.csv                          |
| test_data_predicted | 测试集预测结果文件名称 | predicted.csv                        |
| eval_data           | 评估结果文件名称    | eval.csv                             |
| features            | 特征          | ['feature1', 'feature2', 'feature3'] |
| predict_target      | 预测目标        | ['target1,' target2']                |
| imageVersion        | 镜像版本        | models:v7                            |

##### Training and Predict
>In the official download run.sh and Config.ini, modify the config to perform the following command training model and get the Predict results, the running process as shown in the following figure.

```
./run.sh config location direatory/config.ini
```
![](https://github.com/BCI-Athena/RevenuePrediction/blob/master/Images/RevenuePrediction-directive.png)
