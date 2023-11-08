Access the AWS Console:

Go to the official AWS Management Console by visiting https://aws.amazon.com/ and signing in to your AWS account.
Open IAM Dashboard:

Once you are logged in, navigate to the IAM (Identity and Access Management) dashboard. You can find this service under the "Security, Identity, & Compliance" category in the AWS Management Console.
Create a New Role:

On the IAM dashboard, locate and click on the "Roles" option in the left-hand navigation pane.
Initiate Role Creation:

In the Roles section, you will see a button labeled "Create role." Click on it to start creating a new role.
Choose Role Type:

In the "Create role" wizard, you will be asked to choose the type of trusted entity that will assume this role. Select "AWS service" and then choose "Amazon EC2" as the use case. Click "Next: Permissions."
Attach Policies:

In the "Permissions" section, you need to specify the policies that grant permissions to the EC2 instances. To attach policies, click on the "Add permissions" button.
Search for Policies:

In the "Add permissions" screen, there is a "Filter policies" search bar. Here, you should search for the following policies and select them:
AWSElasticBeanstalkWebTier
AWSElasticBeanstalkWorkerTier
AWSElasticBeanstalkMulticontainerDocker
Review and Name:

After selecting the necessary policies, click "Next: Tags" if you want to add any tags. Then, click "Next: Review" to proceed to the final configuration.
Name the Role:

Provide a meaningful name for your role. For this guide, let's call it "ec2instanceprofilerole."
Create the Role:

Review the role details, and when everything looks correct, click "Create role" to finalize the process.
Launching an Elastic Beanstalk Environment:

Access AWS Elastic Beanstalk:

In the AWS Management Console, go to the Elastic Beanstalk dashboard.
Create or Select an Application:

If you don't already have an Elastic Beanstalk application, click on "Create Application." Otherwise, select the existing application to which you want to add the environment.
Navigate to Environments:

In the left navigation pane, click on "Environments" to manage your Elastic Beanstalk environments.
Create a New Environment:

Click the "Create Environment" button to initiate the environment creation process.
Environment Information:

In the "Environment Information" section:
Choose "Web server environment" as the environment tier.
Fill out other environment details, including application name, platform, environment name, and domain configuration.
Base Configuration:

<img width="1440" alt="Screenshot 2023-11-07 at 10 30 02 AM" src="https://github.com/Vishnu5L3/Serverless-Lab-Design/assets/142379885/83e84394-2792-4442-8302-07a27d049bec">

<img width="1440" alt="Screenshot 2023-11-07 at 10 30 11 AM" src="https://github.com/Vishnu5L3/WORDPRESS-Deployment/assets/142379885/c835068f-c610-452b-a84c-0f321482f5fa">



Under "Base Configuration," select "Upload your code" and click "Upload" to choose the local ZIP file containing the WordPress files that you previously downloaded from wordpress.org.
Configuration:

In the "Configuration" section, you can further customize your environment settings.
Service Role Selection:

In the "Service role" option, select the instance profile role you created earlier, which should be named "ec2instanceprofilerole."
Database Configuration:

<img width="1440" alt="Screenshot 2023-11-07 at 12 08 31 PM" src="https://github.com/Vishnu5L3/Serverless-Lab-Design/assets/142379885/5f963dd9-afd1-4ff9-9455-92b799e6a3ef">


Configure the database settings as needed. Select "MySQL" as the database engine, choose the desired database instance class, and provide a username (e.g., "admin") and a secure password.
Review and Launch:

<img width="1440" alt="Screenshot 2023-11-07 at 10 34 11 AM" src="https://github.com/Vishnu5L3/Serverless-Lab-Design/assets/142379885/540fb868-b3f0-4629-876b-0358cb81f7e2">



Carefully review all the settings you've configured for your Elastic Beanstalk environment. Once you're satisfied, click the "Create environment" button to launch the environment.

<img width="1440" alt="Screenshot 2023-11-07 at 12 12 34 PM" src="https://github.com/Vishnu5L3/WORDPRESS-Deployment/assets/142379885/7ffeda14-1b61-42d3-b9b2-ced9040e598b">

<img width="1440" alt="Screenshot 2023-11-07 at 12 19 50 PM" src="https://github.com/Vishnu5L3/WORDPRESS-Deployment/assets/142379885/2bcf09e1-9839-43ff-b628-f9c541599d35">



Accessing RDS Database Settings:

Go to RDS Console:

Once your Elastic Beanstalk environment is successfully deployed, go to the Amazon RDS (Relational Database Service) dashboard in the AWS Management Console.
Select Your RDS Database:

<img width="1440" alt="Screenshot 2023-11-07 at 12 24 22 PM" src="https://github.com/Vishnu5L3/WORDPRESS-Deployment/assets/142379885/6eed6c19-3e04-4ec8-a820-81dc7f4e2898">


Locate and select the RDS database that was automatically created by your Elastic Beanstalk environment.
Navigate to Database Settings:

In the left navigation pane, click on "Configuration" to access your database settings.
Retrieve Endpoint and Database Name:

Under "Security groups," you will find the endpoint link and the name of the database. Copy both pieces of information.
Configuring WordPress:

Open the WordPress Link:

Open the WordPress link provided by your Elastic Beanstalk environment in a web browser.
Database Information:

You will be prompted to enter specific database information to complete the WordPress setup:
Database Name: Provide the name of the database (the one you copied from the RDS# WORDPRESS-Deployment

<img width="1440" alt="Screenshot 2023-11-07 at 12 25 36 PM" src="https://github.com/Vishnu5L3/WORDPRESS-Deployment/assets/142379885/b3e53f5d-61dc-44b1-9875-610b9826c90e">


<img width="1440" alt="Screenshot 2023-11-07 at 12 27 08 PM" src="https://github.com/Vishnu5L3/WORDPRESS-Deployment/assets/142379885/ce211624-58da-46ec-bd9b-4b5cbd9c4b2e">



<img width="1440" alt="Screenshot 2023-11-07 at 12 28 04 PM" src="https://github.com/Vishnu5L3/WORDPRESS-Deployment/assets/142379885/b06782d5-5376-42ad-b2c8-281d6aa1224c">










