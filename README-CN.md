# 介绍

> BAIOPS 营销预测项目

# 入门

1. 安装 docker 包

   > Ubuntu安装

   ```
   apt-get install docker
   ```

   > CentOS / RHEL[Red Hat Enterprise Linux]安装

   ```
   yum install docker
   ```

   > MacOS安装

   从下面的链接下载dmg文件：
   ​    

   ```
   https://download.docker.com/mac/stable/Docker.dmg
   ```

   或者
   ​    

   ```
   brew cask install docker
   ```

2. 获取镜像

   ```
    docker pull BAIOPS/RevenuePrediction:v1.0
   ```

3. 下载run.sh 脚本
   ​      

   ```
    需要一个网络路径放置这个脚本，可以放到BAIOPS的Azure上面，然后给个路径
    wget http://baiops.com/files/run.sh
   ```

4. 为run.sh脚本添加可执行的权限 

   ```
    chmod +x run.sh
   ```

5. 现在运行run.sh，添加您的数据文件路径，您可以看到预测结果

   ```
    ./run.sh -input your_data_file.csv [-config config.ini]   
   ```

6. 实例结果:

   ```
    把示例输出结果赋值到这里
   ```
   
# 营销模型说明

>该模型主要对用户消费进行预测，只需输入训练数据集并指定特征及预测目标即完成预测模型的训练，同时可利用测试集对模型进行评估。如下图所示，训练特征有基本信息：年龄、性别、地域、行业，消费能力：消费周期、消费金额、消费级别，浏览记录：浏览时长、浏览商品；预测目标为消费金额（特征及目标不限于这些，不同行业可自行定制）。

![](https://github.com/BCI-Athena/RevenuePrediction/blob/master/Images/RevenuePrediction.JPG)

##### 训练数据集：

+ 数据集格式：csv文件格式
+ 特征：支持数值型、字符型，建议为数值型
+ 预测目标：数值型
+ 注意：数据集需经过预处理，不允许有空值存在

##### 测试数据集：

+ 数据集格式：csv文件格式
+ 特征：支持数值型、字符型，建议为数值型
+ 预测目标：数值型
+ 注意：数据集需经过预处理，不允许有空值存在；需要包含预测目标，用于评估模型

##### 配置文件说明

>可在官方下载config.ini，用户对该文件进行修改对数据集、特征、预测目标及镜像版本进行配置，各配置如下表所示：

| **Key**             | **说明**      | **样例**                               |
| :------------------ | :---------- | :----------------------------------- |
| data_dir            | 数据集存放目录     | /home/hb/docker_file                 |
| train_data          | 训练集文件名称     | train_1w.csv                         |
| test_data           | 测试集文件名称     | test_2k.csv                          |
| test_data_predicted | 测试集预测结果文件名称 | predicted.csv                        |
| eval_data           | 评估结果文件名称    | eval.csv                             |
| features            | 特征          | ['feature1', 'feature2', 'feature3'] |
| predict_target      | 预测目标        | ['target1,' target2']                |
| imageVersion        | 镜像版本        | models:v7                            |

##### 训练并预测

>可在官方下载run.sh和config.ini,修改配置文件执行如下命令训练模型并得到预测结果，运行过程如下图所示。

 ```
./run.sh config所在目录/config.ini
 ```
