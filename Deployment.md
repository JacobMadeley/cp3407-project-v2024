## Deployment Method
This project was deployed to an Amazon Web Service cloud system using AWS with the elastic beanstalk module.

Initially it was expected this would take approximately 2 hours with four of us working on it, however, it took 14 hours.
![image](https://github.com/JacobMadeley/cp3407-project-v2024/assets/110138379/0de52a39-40d1-48d6-8664-e12fb0f164dd)

To explain the process:
A service user had to be created that would act as an intermediary between the environment and the RDS server.
An EC2 user was created specifically for the EC2 handling components.
These user roles were created in the IAM AWS.
![image](https://github.com/JacobMadeley/cp3407-project-v2024/assets/110138379/06e39531-6e0d-4759-ade5-e26520fc7470)

The application had to be extensively tweaked for deployment, and migrated to an RDS(remote database server) as the deployed project in AWS does not have a local database.
The RDS had to contain a VPC(virtual private cloud) with a security system that needed specific rules for in and outbound traffic, and rules to link to the EC2 configuration.
![image](https://github.com/JacobMadeley/cp3407-project-v2024/assets/110138379/8c28c037-ccf9-46ff-8bd7-7181c5b756c4)
![image](https://github.com/JacobMadeley/cp3407-project-v2024/assets/110138379/cfbafe64-ec69-45a6-aea9-3b20bea80a04)
![image](https://github.com/JacobMadeley/cp3407-project-v2024/assets/110138379/ddbb9367-2dd4-4c48-9746-f689af2d9316)

The deployed version is live and available at this link:
http://hotelbookingapp-env1.ap-southeast-2.elasticbeanstalk.com/dashboard/
It connects to the same database as the local version of the app, so a hotel could have the program as a local application with an onsite database, or a completely cloud based solution.

Unfortunately it was discovered upon successful deployment that our method of handling CSS styles was incompatible with the deployed webapp version of Django, as it cannot serve static files to Django natively.
This fact was not mentioned in the three different tutorials/blogs the team followed for methodolgy, and it was only after deployment where this issue was investigated that it was discovered that if you intend to deploy a project, you have to structure the project differently from the start.
The next time our team builds a project using this deployment method and dev tools, this will be taken into consideration and properly implemented.

As a consequence of this, the Navigation Bar and some images do not render correctly, however, they are still present and interactable, as can be seen using the select all(ctrl + a) keyboard shortcut.
![image](https://github.com/JacobMadeley/cp3407-project-v2024/assets/110138379/bce2d491-8c6a-4213-834f-0331e9aa3f83)
It will display the same data from the same database as the local version, and the html POST requests still function. The issues are purely visual.

