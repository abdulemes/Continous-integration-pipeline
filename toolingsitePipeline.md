# Project Workflow

## Setting up VM Environment

Step 1 - Ubuntu server was spinned up on AWS EC2 instance for jenkins.

![IMG_9846](https://user-images.githubusercontent.com/93732510/164970298-ec40b6d9-38ea-4f42-853a-87eecb7434d9.jpg)

## Installing Jenkins 

Step 1 - Apt package manager was first updated and then JDK intstalled since Jenkins is a java-based application.

![IMG_9836](https://user-images.githubusercontent.com/93732510/164970536-c417522a-4e2b-4a87-9e86-14380ffa3959.jpg)

Step 2 - To install jenkins, a bash script was prepared to run all the necessary commands.

![IMG_9837](https://user-images.githubusercontent.com/93732510/164970645-db9534e7-9d67-4478-8ae3-b0e0efd63bfd.jpg)

![IMG_9838](https://user-images.githubusercontent.com/93732510/164970693-48e106c3-cbe0-4001-a7dd-1a27629cb9a2.jpg)

Step 3 -  Jenkins server status was checked to verify it has been successfully installed and active.

![IMG_9839](https://user-images.githubusercontent.com/93732510/164970807-54b332d5-147d-4764-9deb-e3562b834551.jpg)

Step 4 - Jenkins default port was opened in the inbound rule of the instance security group.

![IMG_9840](https://user-images.githubusercontent.com/93732510/164970953-3f82ef13-4a5b-4c60-a0e9-0861f94f82f8.jpg)

Step 5 - Jenkins was accssed via browser and secret password entered.

![IMG_9843](https://user-images.githubusercontent.com/93732510/164971025-e8525bc3-9da8-419a-b463-3a19f4e7678b.jpg)

## Configuring Jenkins to retrieve source code from github using webhook

Step 1 - Webhook was enabled in github repository settings.

![IMG_9844](https://user-images.githubusercontent.com/93732510/164971123-df8db69a-8ce2-4efa-9a34-b1a9d03380d1.jpg)

Step 2 - First job was created on jenkins as a freestyle project.

![IMG_9845](https://user-images.githubusercontent.com/93732510/164971217-d26c728d-42a7-4bd2-92c0-11dc00013214.jpg)

![IMG_9847](https://user-images.githubusercontent.com/93732510/164971293-2e16e14d-c4e5-49ae-9ac3-d0b8a1721d67.jpg)

Step 3 - TO make the run automatically, in the configure tab, github hook trigger was selected so the job can run when a commit is made.

Step 4 - In the post build action, archive arifacts was selected so the artifacts generated from the build job can be stored.

Step 5 - A change was made in the readme file to and verified that the build job ran after the commit.

![IMG_9849](https://user-images.githubusercontent.com/93732510/164971656-16f18878-47ff-480d-8e45-08baa38632ed.jpg)

## Configuring Jenkins to copy the artifacts to NFS server

Step 1 - For jenkins to store the artifacts to NFS server, push over ssh plugin was used.

![IMG_9850](https://user-images.githubusercontent.com/93732510/164971815-416a5756-ad3c-404a-9ceb-0d0c3a8064c1.jpg)

Step 2 - Credentials needed for jenkins to connect o NFS server configured.

![IMG_9852](https://user-images.githubusercontent.com/93732510/164972027-115cdd81-1915-4bc1-94e5-1dd761ab774e.jpg)

Step 3 - In the post build action, all files and directory was configured for jenkins to publish to NFS server.

![IMG_9853](https://user-images.githubusercontent.com/93732510/164972171-2c5048fc-f4eb-4d02-b46d-5c3b07a1b989.jpg)

Step 4 - A change was made in github readme file so jenkins can start the build job and deploy artficats to NFS server as configured.

![IMG_9854](https://user-images.githubusercontent.com/93732510/164972306-96aa955d-ca65-49ff-a4bc-1e5e788fee80.jpg)
