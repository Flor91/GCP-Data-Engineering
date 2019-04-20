---
title: Google Cloud Platform Big Data and Machine Learning Fundamentals
created: '2019-04-20T01:57:05.966Z'
modified: '2019-04-20T12:14:52.643Z'
---

# 1. Google Cloud Platform Big Data and Machine Learning Fundamentals

### Overview: 
 Introduction to the Big Data and Machine Learning capabilities of Google Cloud Platform (GCP). It provides a quick overview of the Google Cloud Platform and a deeper dive of the data processing capabilities.

At the end of this course, we will be able to:
• Identify the purpose and value of the key Big Data and Machine Learning products in the Google Cloud Platform

• Use CloudSQL and Cloud Dataproc to migrate existing MySQL and Hadoop/Pig/Spark/Hive workloads to Google Cloud Platform

• Employ BigQuery and Cloud Datalab to carry out interactive data analysis

• Choose between Cloud SQL, BigTable and Datastore

• Train and use a neural network using TensorFlow

• Choose between different data processing products on the Google Cloud Platform

## What is the Google Cloud Platform?
Cloud computing is a continuation of a long-term shift on how computing resources are managed.
- First Wave *[1980 - 2000]* - **Server on-premises**: Each company owns everything, it is their job to manage it.
- Second Wave *[2000 - Now]* - **Data centers**: Companies pay for the hardware but rent the space. It is still theirs to manage.
- First Generation Cloud *[Now - Next]* - **Virtualized data centers**: Companies rent hardware and software, but still control and configure virtual machines. Pay for what they provision.


### [Compute Engine](https://cloud.google.com/compute/)
*Scalable, High-Performance Virtual Machines: Compute Processing Units on-demand*
**Compute power**: CPUs on the cloud are provided by a compute engine of virtual machines. 
**Data storage**: Persistent data is stored on Cloud Storage.
**Networking**: Connection between storage and CPU is through a private network. Allows us to have a global scale data and compute infraestructure. 

Caracteristics:
- **Custom machine types**: depending on the HD, CPUs, GPUs needed. Every type comes with capabilities built in: Load balancing, advanced networking monitoring, clustering container support, etc.
- **Preemptible machines**: Great discount on, in return for your flexibility in letting go of it when you don't need it.
- **Automatic discounts**: Rather than ask you to try to determine which of your workloads you're going to be running for long periods of time, GCP gives you a discount after the fact. So at the end of the month, if it turns out that you've used the machine for 60% of the month, you will automatically get a 15% discount.

### [Cloud Storage](https://cloud.google.com/storage/)
*Persistent storage and staging area ground for importing data from outside sources to other Google Cloud products*

1. Import / Extract data from any source storage
2. Process data - could be on Compute Engine
3. Storing raw data in any format, directly onto cloud storage: Cloud storage is persistent storage, it's durable, it's replicated. It can be made globally available if you need to. The simplest way is to use a command line / web service tool called **gsutil**.

 3.1. Buckets: basic containers that hold your data. Everything that you store in Cloud Storage must be contained in a bucket. You can use buckets to organize your data and control access to your data, but unlike directories and folders, you cannot nest buckets. Because there are limits to bucket creation and deletion, you should design your storage applications to favor intensive object operations and relatively few buckets operations. When you create a bucket, you specify a globally-unique name, a geographic location where the bucket and its contents are stored, and a default storage class. The default storage class you choose applies to objects added to the bucket that don't have a storage class specified explicitly.

 3.2. Once you have your data on cloud storage you can control access to it at:
  - that object level;
  - at that bucket level: Every bucket belongs to a project, and a project is essentially the way you do billing, etc, in GCP. So essentially, when you create a bucket in a project, you are basically saying, which billing account is going to be responsible for paying for the storage;
  - at that project level: You can say people who are editors on this project can also add and remove files from this particular bucket;
  - make access control to all authenticated users: anybody who's logged in with a Google account, you can provide access to them;
  - provide access to all users: they don't even need to be logged in, they can just come and get the data that you have. 

 3.3. Use multiple zones in a region to minimize the impact of service disruptions. And use multiple regions to provide global access to your application.

7. Once data is in the GCStorage we can input it into Cloud SQL, into BigQuery, into Dataproc, into variety of the different analysis tools and data bases. You could also use that to take the data from cloud to a local SSD disk on a compute engine VM, so that if you're going to be reading some data routinely all the time, you might want to move it from cloud storage into local.



