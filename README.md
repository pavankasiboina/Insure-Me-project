( 𝐂𝐈/𝐂𝐃 𝐩𝐢𝐩𝐞𝐥𝐢𝐧𝐞 𝐟𝐨𝐫 𝐈𝐧𝐬𝐮𝐫𝐞-𝐌𝐞 𝐚𝐩𝐩𝐥𝐢𝐜𝐚𝐭𝐢𝐨𝐧 𝐭𝐨 𝐜𝐨𝐧𝐭𝐚𝐢𝐧𝐞𝐫𝐢𝐳𝐞𝐝 𝐚𝐧𝐝 𝐝𝐞𝐩𝐥𝐨𝐲 𝐨𝐧 𝐀𝐖𝐒 (𝐏𝐫𝐨𝐝 & 𝐓𝐞𝐬𝐭 𝐒𝐞𝐫𝐯𝐞𝐫𝐬) 𝐰𝐡𝐢𝐜𝐡 𝐜𝐨𝐧𝐟𝐢𝐠𝐮𝐫𝐞𝐝 𝐨𝐯𝐞𝐫 𝐀𝐧𝐬𝐢𝐛𝐥𝐞 𝐟𝐫𝐨𝐦 𝐣𝐞𝐧𝐤𝐢𝐧𝐬 )

This project will be all about how to test the services and deploy insure-me app to dev/stage/prod etc, just on a click of button.

Agenda:
As soon as the developer pushes the updated code on the GIT master branch, the Jenkins job should be triggered using a GitHub Webhook and Jenkins job should be triggered, The code should be checked out, compiled, tested, packaged and containerized and deployed to the preconfigured test-server automatically.

The deployment should then be tested using a test automation tool (Selenium), and if the build is successful, it should be deployed to the prod server. All this should happen automatically and should be triggered from a push to the GitHub master branch.


I have implement Continuous Integration & Continuous Deployment for insure-me using following tools:
✓ Git - For version control for tracking changes in the code files
✓ Jenkins - For continuous integration and continuous deployment
✓ Docker - For building docker images & deploying containerized applications on registry
✓ Ansible - Configuration management tool to configure the required packages/software on test & prod servers
✓ Selenium - For automating tests to the the basic functionality of insure-me apllication
✓ AWS : For creating ec2 machines as servers(test & prod) and deploy the insure-me application.


- create the mavanized spring-boot project structure and build the micro service application which performs CRUD operations.
- Write the required Junit Test cases for our project to test the service methods of our project.
- Run the application and check whether the application is accessible on the specified port number or not. (Here in spring-boot application, we no need to explicitly deploy   our application on Tomcat Server, For spring-boot project by default Tomcat is embedded to it)
- Open GitHub and create seperate remote repository to store code of insure-me application
- Initialize the local git repository on your local machine, i:e Where your code is present and push the changes of your code to git hub repository by adding/connecting both local repo and remote repository.
- Now Configure the Jenkins Server in AWS environment on ( EC2 instance ) to establish CI/CD.
- Now create a Jenkins job as a pipeline to build our insure-me project

𝑴𝒂𝒊𝒏 𝑱𝒆𝒏𝒌𝒊𝒏𝒔 𝑷𝒊𝒑𝒆𝒍𝒊𝒏𝒆:
  = First stage in our pipeline would be the git checkout
  = Second stage is to clean, compile, test and package using maven
  = Third stage is to Build a docker image
  = The next stage i:e Fourth stage in our Jenkins pipeline is to deploy our image to the docker registry (Dockerhub)
  = The next stage is configuring the ansible to deploy our image in the Test Server.
  
- Now write the selenium scripts to test the functionality of insure-me app and generate the executable jar of selenium scripts of our insume-me
- Create seperate github repository Push the both selenium code and runnable jar to the github repository

𝑺𝒆𝒍𝒆𝒏𝒊𝒖𝒎 𝑱𝒆𝒏𝒌𝒊𝒏𝒔 𝑷𝒊𝒑𝒆𝒍𝒊𝒏𝒆:
- Create a separate Jenkins pipeline to test selenium scripts and to run the selenium runnable jar
- If the build is successful in the selenium pipeline and then make sure you connect this pipeline with the main Jenkins pipeline .
- selenium pipeline will only execute after the main Jenkins pipeline build is successful.
   

𝑷𝒓𝒐𝒅𝒖𝒄𝒕𝒊𝒐𝒏 𝑱𝒆𝒏𝒌𝒊𝒏𝒔 𝑷𝒊𝒑𝒆𝒍𝒊𝒏𝒆:
- Now we need to deploy our application into production server automatically after the selenium pipeline job successful.
- Write the ansible playbook file to deploy and configure the application insure-me on to the production server.
- Now write a separate Jenkins pipeline to do this above job automatically.
 
Make sure that this pipeline will be only execute only after the selenium pipeline 
executed successfully.

That is, at last we have achieved the complete automation of deployment of 
insure-me application delivering from development to production with a single 
hit button. 





