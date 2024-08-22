# Overview of Project 
Amazon QuickSight is a fully managed cloud-scale business intelligence service that is powered by machine learning and allows you to create data visualizations and dashboards for the people you work with, wherever they are.

In this project, you'll explore how to create visualizations using Amazon QuickSight with a large dataset stored in Amazon S3. Specifically, you'll work with a dataset containing information on 50,000 of the best-selling products on Amazon.com.

# Step #1: Download the Dataset
*  Download the "Amazon Bestseller Dataset.csv" file along with the "manifest.json" file to your local machine.
*  Click on "raw" and Control+S to save both files onto your computer.

# Step #2: Store the Dataset in Amazon S3
* Open the Amazon S3 console and click "Create Bucket".
* Name the bucket and keep the settings as default.

  ![quicksite](https://github.com/user-attachments/assets/b1f04fc7-dfaf-426b-a7b2-737974b8986b)

* Upload the CSV file and the "manifest.json" file into the bucket.

  ![quicksite-2](https://github.com/user-attachments/assets/34471c91-c6ef-4a53-93ba-91051da5737f)

  Note: Replace the URL in the "manifest.json" file with the S3 URL of your dataset.

# Step #3: Connect S3 Bucket with Amazon Quicksight
* Open the AWS management console and navigate to Amazon Quicksight.
* Sign up for a free trial of the Enterprise edition if you don't have an account.
* Enter a unique name for your QuickSight account, used for signing in.
* Select only the necessary services, and in the services section, choose S3 and select your bucket.

  ![quicksite-3](https://github.com/user-attachments/assets/fd970ad4-8a16-4cca-9354-c403f96fed2e)

* In your account, go to Datasets and create a new dataset.
* Choose S3 from data sources.

   ![quicksite-5](https://github.com/user-attachments/assets/e01cda39-fd6f-4973-9caf-f28a85932f16)

* Enter the link to your "manifest.json" file and connect to Quicksight.

  ![quicksite-6](https://github.com/user-attachments/assets/c8133234-845b-4bdc-9a1e-4130be6bbb51)

* Select visualize and create.
  
  ![quicksite-7](https://github.com/user-attachments/assets/1abefd41-8b56-4d8f-aa61-b0ae5f4ff8df)

  ![quicksite-8](https://github.com/user-attachments/assets/bf44c39b-8e50-4e19-a797-7612f4d5c99f)

* You can now start creating visualizations.

  ![quicksite-9](https://github.com/user-attachments/assets/44b6e361-1185-4e94-bb8e-efd56c417c5a)

# Step #4: Create Visualizations  
* Drag fields into the graph to create visualizations (e.g., brand, categories, price).

  ![quicksite-10](https://github.com/user-attachments/assets/239ae9e3-ff5f-49cc-8b68-ce4027bd2aab)

* Sort, filter, and customize the graphs as desired.

  ![quicksite-11](https://github.com/user-attachments/assets/6d7ca50b-07dd-4130-af2d-79eace30cfa8)

  ![quicksite-13](https://github.com/user-attachments/assets/79e1cf79-84be-463b-911e-f0ed342afb72)

* Experiment with different types of graphs like bar charts, pie charts, line graphs, etc.

  ![quicksite-14](https://github.com/user-attachments/assets/5a191d96-ce9d-463b-a852-29919cdfa77c)

  ![quicksite-15](https://github.com/user-attachments/assets/be268edd-14da-4446-9d85-f60e13d59a5e)


  

  



  

  


  


  





  



  




