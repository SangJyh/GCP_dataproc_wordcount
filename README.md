# This Project is for Cloud Map Reduce and Distributed Jobs

## Introduction

Google Cloud Platform (GCP) has data lake platform call Dataproc that allow users to perform mapreduce and distributed jobs easily.

This project is to demo Dataproc perform classic mapreduce work - word count for Shakespeare's paper. The workflow will be shown step by step:

### Setup cluster and bucket for mapreduce work on Dataproc

![](demopic\Picture1.png)

In GCP console, we search *dataproc* and create cluster for this project in *Clusters* tab. 

![](/demopic/Picture3.png)

We can also set up the configuration for this cluster such as machine type or work nodes.

![](demopic\Picture4.png)

We can see the Status of the cluster and the bucket connected to this cluster. After the cluster status is running, we can click the cluster name for job submission and running VM instances.

![](demopic\Picture5.png)

We first select the *VM Instance* and click the `SSH` to logistic work.

![](demopic\Picture6.png)

In the SSH interface, we can use `pwd` to check our working directory, we can also find that Google has compiled the apache spark examples into a jar file.

![](demopic\Picture7.png)

We go back to the working directory and check our hadoop version, since we need to specify the correct hadoop version for the mapreduce work later! In this tutorial, we can find that the hadoop version is 3.2.2.

We can also make the directory in Hadoop using `hadoop fs -mkdir folder_name` command.

![](demopic\Picture8.png)

GCP allows users easily upload their files using the setting icon in the SSH interface.

![](demopic\Picture9.png)

We can also check if our file upload correctly.

![](demopic\Picture11.png)

Another way to upload the file is to use the *bucket* interface to upload the data. If you do so, you can check the file url by clicking the file (as shown in the following picutre).

![](demopic\Picture14.png)


*Now, we are good to go*


### Mapreduce using Dataproc

![](demopic\Picture10.png)

We go back to our Dataproc and click the cluster we will use for mapreduce workflow. Here, I select *hadoop-demo*.

![](demopic\Picture15.png)

We click the SUBMIT JOB button and set up the configuration for this job. Remember the Job name, Main class or jar, Jar files, and Arguments are imutable, so make sure they are correct and unique before we run them.

![](demopic\Picture16.png)

Here is my configuration of my wordcount mapreduce work

![](demopic\Picture16.png)

It will take few seconds to run. After the Status is Succeeded, we can go to the *bucket* and find our output as shown below

![](demopic\Picture18.png)

![](demopic\Picture21.png)

Go to the output folder, we can find the wordcount results are shown in the picture. We can download the result to local using the download icon easily.

![](demopic\Picture21.png)

This is the wordcount result!

*Now you know how to perform the mapreduce work on GCP!*
