# CI MERGE - Jenkins
# What is Jenkins as well as as what other tools available 

Jenkins is a DevOps tool where central build and continous integration takes place. It is an open-source automation server and is a Java based program. It allows us to automate parts of the development process. 

# Jenkins stages

![image](https://user-images.githubusercontent.com/129324316/235670477-7f4b0903-4b8a-481f-ac9d-b972016026af.png)

![image](https://user-images.githubusercontent.com/129324316/235731482-e0536549-2da0-47d1-b997-ceb3b5e19a63.png)

# CI test integration testing


# What is the diff between continuous delivery CD and Continuous deployment CDE

| Continuous Delivery      | Continuous Deployment |
| ----------- | ----------- |
| Continuous delivery produces artifacts deployable to production, but a human must still push the button to deploy the release      |  Continuous deployment involves deploying every push to production automatically, without human intervention       |
| Continuous delivery focuses on the release and release strategy   | Continuous deployment focuses on the actual deployment        |


# Jenkins Steps:
Pre-requisites:
Have the `app` folder in a repository where the `test` folder is.

## Generating the keys

1. Generate a new ssh key following these steps: https://github.com/fsh-nur/tech221_ssh
2. Name the key: `fatima-jenkins-key`
3. Make sure to attach your `public key` to your repo which is includes the `app` folder:


![1  keys](https://user-images.githubusercontent.com/129324316/235736517-e5725b88-cd8b-426a-b753-ec8a6a6da306.png)

## Accessing Jenkins and testing your app

1. Enter the Jenkins interface through this ip: `http://35.178.11.196:8080/login?from=%2F`
2. Log in with your details
3. Create a job

![1  create job](https://user-images.githubusercontent.com/129324316/235740164-0f49aae6-f8eb-4b09-9e66-7b87fbd24c63.png)

2. Enter a name and choose `Freestyle Job`

![2  descriotion](https://user-images.githubusercontent.com/129324316/235740385-2e8abad2-6469-4fb1-a5f0-446bee7741d0.png)


3. Enter the description of the job, and consequently add the maximum amount of builds according to the amount the server can take. Enter the **HTTPS** link to your repo.

![3](https://user-images.githubusercontent.com/129324316/235741087-3221ea90-6758-41c3-a8c8-f17ec0bd0db3.png)

4. Follow these instructions. You can access your private key using the `cat` command in GitBash 

![4](https://user-images.githubusercontent.com/129324316/235745991-edb86602-5087-4573-af5d-499411b27d66.png)

5. Configure the build environment


![5](https://user-images.githubusercontent.com/129324316/235746848-2d057b6c-a599-4642-ac66-c5f85b30ca85.png)

6. Choose `execute shell` when selecting `Build Actions` and enter the following commands to conduct the tests within the `test` folder:


![6](https://user-images.githubusercontent.com/129324316/235755533-ef8c92c7-fa39-4711-a423-6410a1de45cb.png)

7. Click `Save`
8. Check the console output to see if the tests ran were a success:

![7](https://user-images.githubusercontent.com/129324316/235755832-214ed2e8-f71e-4291-b9f6-c4580e942dc3.png)

9. You should see this at the end of your script.


![8](https://user-images.githubusercontent.com/129324316/235756445-6456788c-2345-4ad6-b4c0-c6c1218b78e8.png)






