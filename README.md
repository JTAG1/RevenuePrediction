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

