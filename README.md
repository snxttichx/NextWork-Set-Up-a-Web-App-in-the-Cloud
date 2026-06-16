<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Set Up a Web App in the Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-vscode)

**Author:** NATTICHA SUKHAWAT  
**Email:** 6631502015@lamduan.mfu.ac.th

---

## Set Up a Web App Using AWS and VS Code

![Image](http://learn.nextwork.org/appreciative_gray_fierce_tapir/uploads/aws-devops-vscode_7a1de541)

---

## Introducing Today's Project!

In this project, I will demonstrate how to launch an Amazon EC2 instance, connect to it remotely using VS Code, and create a basic Java web application in AWS. I'm doing this project to learn the fundamentals of cloud computing, remote server management, and the first steps of building a CI/CD pipeline.

This project is part one of a series of DevOps projects where I’m building a CI/CD pipeline. I’ll be working on the next project after completing my current learning module and reviewing what I’ve done here, so I can fully understand each step before moving on to the next stage.

I did this project because I wanted to learn how real-world cloud development works and how developers use AWS services together with tools like VS Code to build and manage applications on remote servers.

### Key tools and concepts

Services I used were AWS IAM, Amazon EC2, SSH, VS Code Remote - SSH, Apache Maven, and Amazon Corretto 8. These services helped me securely access a cloud server, set up a development environment, and build a Java web application.

Key concepts I learnt include how to manage cloud access safely using IAM instead of the root account, how remote development works through SSH connections, how IDEs like VS Code can interact directly with cloud servers, and how tools like Maven manage project structure and dependencies for Java applications.

### Project reflection

This project took me approximately a few hours to complete, including setup, installation, and practicing the different tools and workflows.

The most challenging part was setting up the environment correctly, especially configuring IAM permissions, installing Java and Maven on the EC2 instance, and making sure the VS Code Remote - SSH connection worked smoothly.

It was most rewarding to successfully run and edit a Java web application on a real cloud server and see how changes made in the terminal were instantly reflected in VS Code.

One thing I didn’t expect in this project was how seamless it felt to work directly on a remote EC2 instance using VS Code. I thought working on a cloud server would feel complicated or slow, but the Remote - SSH setup made it feel almost like I was working on a local machine, with files updating instantly across terminal and IDE sessions.

---

## Launching an EC2 instance

### What I did in this step

In this step, I will launch an Amazon EC2 instance, create a key pair, and configure its network settings because the EC2 instance will serve as the cloud server where I build and run my web application.

I started this project by launching an EC2 instance because it provides a virtual server in the cloud where I can develop, store, and run my web application without needing physical hardware.

![Image](http://learn.nextwork.org/appreciative_gray_fierce_tapir/uploads/aws-devops-vscode_7852fbf3)

### I also enabled SSH

SSH is a secure network protocol that allows authorized users to access and manage a remote server. I enabled SSH so that I could securely connect to my EC2 instance and manage it remotely using encrypted communication.

### Key pairs

A key pair is a set of cryptographic keys used to securely access an EC2 instance. It consists of a public key stored by AWS and a private key stored on your computer, which work together to verify your identity and allow secure access to the server.

### Downloaded key pair file

Once I set up my key pair, AWS automatically downloaded a .pem private key file to my local computer. This file is used to securely authenticate and connect to my EC2 instance.

---

## Set up VS Code

### What I did in this step

In this step, I will install VS Code, set up a terminal, and configure my key pair permissions because I need a secure way to connect to my EC2 instance and create and edit my web application's code remotely.

### What is VS Code?

VS Code (Visual Studio Code) is a lightweight and powerful code editor developed by Microsoft. It allows developers to write, edit, and manage code, use an integrated terminal, and connect to remote servers such as EC2 instances for application development and management.

I installed VS Code to connect to my EC2 instance remotely, use the integrated terminal, and write, edit, and manage my web application's code directly from my computer.

![Image](http://learn.nextwork.org/appreciative_gray_fierce_tapir/uploads/aws-devops-vscode_53d05e68)

---

## My first terminal commands

A terminal is a command-line interface where you interact with your computer by typing text commands instead of clicking buttons. The first commands I ran for this project were D: and cd NextWork_DevOps, which opened my D drive and navigated to the folder containing my project files and EC2 key pair.

### Updating file permissions

I also updated my private key's permissions by using the icacls commands to remove existing permissions, grant read access only to my Windows user account, and disable inherited permissions. This ensured that only I could access the .pem file, which is required for secure SSH authentication with my EC2 instance.

![Image](http://learn.nextwork.org/appreciative_gray_fierce_tapir/uploads/aws-devops-vscode_9328ada1)

---

## SSH connection to EC2 instance

### What I did in this step

In this step, I will connect to my EC2 instance using SSH from VS Code because I need secure remote access to the virtual server so I can manage files, install software, and develop my web application directly on the cloud server.

### Connecting to EC2

To connect to my EC2 instance, I ran the command `ssh -i <path-to-key>/nextwork-keypair.pem ec2-user@<public-dns>`, which used my private key and the instance's Public DNS to establish a secure SSH connection to the server.

### This command required an IPv4 address

A Public DNS (Domain Name System) is the public address of an EC2 instance that allows users and applications to find and connect to the server over the internet. Instead of using the server's public IP address, you can use the Public DNS name to access the EC2 instance.

![Image](http://learn.nextwork.org/appreciative_gray_fierce_tapir/uploads/aws-devops-vscode_e3069dca)

---

## Maven & Java

### What I did in this step

In this step, I will install Apache Maven and Amazon Corretto 8 on my EC2 instance because they provide the tools needed to build, compile, and run a Java web application in the cloud.

### Why I'm using Maven

Apache Maven is a build automation and project management tool for Java applications. It helps developers organize projects, manage dependencies, and generate project templates, making it easier and faster to build and develop Java web applications.

Maven is required in this project because it helps manage dependencies, automate the build process, and generate the basic structure of a Java web application, making development faster and easier.

### Why I'm using Java

Java is a programming language used to build applications, and Amazon Corretto 8 is Amazon's free distribution of Java. We installed Amazon Corretto 8 because Maven requires Java to run and build our web application.

Java is required in this project because Maven depends on Java to run, and Java provides the environment needed to build, compile, and run our web application on the EC2 instance.

---

## Create the Application

### What I did in this step

In this step, I will use Maven commands to generate a Java web application because Maven can automatically create the project's structure and required files, allowing me to start developing the application quickly and efficiently.

### Creating the Java web app

I generated a Java web app using the command mvn archetype:generate -DgroupId=com.nextwork.app -DartifactId=nextwork-web-project -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false, which used a Maven archetype to automatically create a basic Java web application structure and its required files.

### Installing Remote - SSH

I installed Remote - SSH, which is a VS Code extension that enables secure connections to remote servers over SSH. I installed it to access my EC2 instance directly from VS Code and use its IDE features to view, edit, and manage my web application's files more efficiently.

### SSH configuration details

Configuration details required to set up a remote connection include the Host and HostName (my EC2 instance's Public DNS), the User (ec2-user), and the IdentityFile (the path to my nextwork-keypair.pem private key). These settings allowed VS Code to securely connect to my EC2 instance via SSH.

![Image](http://learn.nextwork.org/appreciative_gray_fierce_tapir/uploads/aws-devops-vscode_2939cf01)

---

## Create the Application

### Exploring the project structure

Using VS Code's file explorer, I could see the nextwork-web-project folder along with its subfolders and files, including the src directory containing the web application's source code and the pom.xml file containing the project's Maven configuration and dependencies.

Two of the project folders created by Maven are src and webapp, which store the application's source code and web resources. The src folder contains the project's source files, while the webapp folder contains files such as JSP, HTML, CSS, and JavaScript that define the web application's content and user interface.

![Image](http://learn.nextwork.org/appreciative_gray_fierce_tapir/uploads/aws-devops-vscode_45f91fd7)

---

## Using Remote - SSH

### What I did in this step

In this step, I will connect VS Code directly to my EC2 instance using the Remote SSH extension because it allows me to view, edit, and manage my web application's files on the server using VS Code's IDE features, such as file navigation and code editing.

### Updating the web app

index.jsp is a Java Server Pages (JSP) file that defines the content of a web page in a Java web application. It is similar to an HTML file but can also contain Java code, allowing the web page to generate dynamic and interactive content.

I edited index.jsp by opening it in VS Code's editor, replacing the placeholder content with my own HTML code, and saving the changes using Ctrl + S.

![Image](http://learn.nextwork.org/appreciative_gray_fierce_tapir/uploads/aws-devops-vscode_7a1de541)

---

## Using nano

### Additional improvements

In this secret mission, I will edit the index.jsp file directly from the terminal instead of using an IDE because it helps me understand how to manage and modify application files on a remote server using command-line tools, which is an important skill for DevOps and cloud engineering.

### Terminal vs IDE

An alternative to using IDEs is editing files directly in the terminal using a command-line text editor. To edit index.jsp, I ran the command nano index.jsp, which opened the file in the Nano text editor so I could modify it directly on my EC2 instance.

Compared to using an IDE, editing index.jsp in the terminal felt more minimal and manual. I had to rely on command-line tools and keyboard navigation, which made simple edits fast but less visual and harder to manage for larger projects.

I’d be more likely to use an IDE if the project is complex, involves multiple files, or requires features like syntax highlighting, autocomplete, debugging tools, and easier file navigation.

### Verifying my work

To verify my editing work in the terminal, I saved the file and then checked the output by running the application through the terminal to confirm that the changes worked as expected.

It was possible to see my changes in VS Code right away because both my terminal session and VS Code Remote - SSH window were connected to the same EC2 instance, so any file changes made through the terminal were instantly reflected in the editor since they were accessing the same remote files.

![Image](http://learn.nextwork.org/appreciative_gray_fierce_tapir/uploads/aws-devops-vscode_a3324ad41)

---

---
